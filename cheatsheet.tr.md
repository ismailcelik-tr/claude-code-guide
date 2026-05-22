# Claude Code — Hızlı Başvuru Kartı

Tüm komutlar, kısayollar ve hook tarifleri tek sayfada.

---

## Slash Komutları

| Komut | Ne Yapar |
|---|---|
| `/init` | Mevcut projeyi tarayıp `CLAUDE.md` taslağı oluşturur |
| `/plan` | Plan moduna girer — Claude uygulamaya başlamadan önce onay bekler |
| `/review` | Mevcut diff'i kod kalitesi açısından inceler |
| `/review --comment` | Review bulgularını GitHub PR'a inline yorum olarak gönderir |
| `/think` | Claude'u daha derin, adım adım düşünmeye yönlendirir |
| `/compact` | Konuşma geçmişini sıkıştırır, bağlamı temizler ama bilgiyi korur |
| `/help` | Kullanılabilir komutların listesini gösterir |
| `/clear` | Konuşmayı temizler, yeni bir oturum başlatır |

---

## Klavye Kısayolları

| Kısayol | Ne Yapar |
|---|---|
| `Esc` | Çalışan işlemi iptal eder |
| `Ctrl + C` | Mevcut görevi durdurur |
| `↑ / ↓` | Önceki mesajlar arasında gezinir |

---

## Prompt Şablonları

### Dosya Düzenleme
```
"[dosya yolu] dosyasındaki [fonksiyon/bölüm] için [ne yapılacak].
 Mevcut [test/yapı]yı bozmadan yap."
```

### Hata Ayıklama
```
"Şu hatayı alıyorum:
 [hata mesajı]
 [dosya yolu] dosyasını oku ve kök nedeni bul."
```

### Test Üretme
```
"[dosya yolu] için unit testler yaz.
 Mevcut test stilini [test dizini] klasöründen öğren."
```

### Plan İsteme
```
"Uygulamaya başlamadan önce planını göster, onaylayayım.
 [görev açıklaması]"
```

### Ajan Görevi
```
"Explore subagent'i kullanarak [ne aranacak].
 Bağlam: [proje bilgisi]
 Döndür: [format]"
```

### Paralel Görev
```
"Şu iki görevi paralel çalıştır:
 1. [bağımsız görev A]
 2. [bağımsız görev B]"
```

### Çıktı Formatı Belirleme
```
"Sonucu şu formatta döndür:
 - Sorun: [ne]
 - Neden: [kök neden]
 - Çözüm: [adımlar]
 - Risk: [yan etkiler]"
```

---

## CLAUDE.md Minimum Şablon

```markdown
# Proje Adı

## Genel Bakış
[1-2 cümle]

## Teknoloji
- [Dil / Framework]
- [Veritabanı]

## Komutlar
- [geliştirme komutu]
- [test komutu]

## Kurallar
- [kural 1]
- [kural 2]
```

---

## settings.json Minimum Şablon

```json
{
  "permissions": {
    "allow": [
      "Bash(npm run *)",
      "Bash(git status)",
      "Bash(git diff *)",
      "Read(**)"
    ],
    "deny": [
      "Bash(rm -rf *)",
      "Bash(git push --force)"
    ]
  },
  "hooks": {
    "PreToolUse": [],
    "PostToolUse": [],
    "Stop": []
  }
}
```

**Dosya konumu:** `~/.claude/settings.json` (global) veya `.claude/settings.json` (proje)

---

## Hazır Hook Tarifleri

### Otomatik Lint (her düzenlemede)
```json
"PostToolUse": [{
  "matcher": "Edit",
  "hooks": [{ "type": "command", "command": "npm run lint --silent 2>&1 | tail -5" }]
}]
```

### Tehlikeli Komut Engelleme
```json
"PreToolUse": [{
  "matcher": "Bash",
  "hooks": [{ "type": "command", "command": "if echo \"$CLAUDE_TOOL_INPUT\" | grep -qE 'rm -rf|drop table|truncate'; then echo 'Engellendi!' >&2; exit 2; fi" }]
}]
```

### Tamamlanma Bildirimi (macOS)
```json
"Stop": [{
  "hooks": [{ "type": "command", "command": "osascript -e 'display notification \"Görev tamamlandı\" with title \"Claude Code\" sound name \"Glass\"'" }]
}]
```

### Commit Öncesi Test
```json
"PreToolUse": [{
  "matcher": "Bash(git commit*)",
  "hooks": [{ "type": "command", "command": "npm test -- --run 2>&1 | tail -10" }]
}]
```

---

## Özel Komut Şablonu

**`.claude/commands/komut-adi.md`:**

```markdown
[Ne yapılacağını açıkla]

Adımlar:
1. [adım]
2. [adım]

$ARGUMENTS  ← parametre almak için
```

Kullanım: `/komut-adi [opsiyonel parametre]`

→ Detay: [Özel Komutlar](./03-hooks-otomasyon/04-ozel-komutlar.tr.md)

---

## Subagent Tipleri

| Tip | Ne Zaman |
|---|---|
| `Explore` | Sadece okuma/araştırma — dosya değiştirmez |
| `Plan` | Uygulamadan önce mimari/yaklaşım onayı |
| `claude` | Araştırma + uygulama birlikte |
| `general-purpose` | Geniş kapsamlı çok adımlı görevler |

---

## Yaygın Hatalar ve Kaçınma Yolları

| Hata | Çözüm |
|---|---|
| Belirsiz görev | Dosya yolu + fonksiyon adı + beklenen davranış ver |
| Görev çok büyük | `/plan` ile parçala, birer birer onayla |
| Claude projeyi unutuyor | Talimatı CLAUDE.md'ye taşı |
| Bağlam doldu | `/compact` çalıştır veya yeni konuşma başlat |
| Ajan yanlış sonuç | Prompt'u bağımsız yaz — önceki konuşmayı bilmiyor |
| Hook tetiklenmiyor | `.claude/settings.json` konumunu kontrol et |

---

## Faydalı Bağlantılar

| Bölüm | Dosya |
|---|---|
| CLAUDE.md nasıl yazılır | [02 › CLAUDE.md](./02-claude-md/README.tr.md) |
| Hook tipleri ve örnekler | [03 › Hooks & Otomasyon](./03-hooks-otomasyon/README.tr.md) |
| Ajan kullanımı | [04 › Ajanlar](./04-ajanlar/README.tr.md) |
| Prompt stratejileri | [05 › Prompt Stratejileri](./05-prompt-stratejileri/README.tr.md) |
| Tam navigasyon | [Ana Sayfa](./README.tr.md) |
