# 02 › CLAUDE.md › İleri Düzey

Import, memory sistemi ve izin yönetimi.

---

## @import ile Parçalama

CLAUDE.md çok büyüdüğünde parçalara böl:

```markdown
# CLAUDE.md

@./docs/architecture.md
@./docs/conventions.md
@./docs/testing.md
```

Her `@` satırı ilgili dosyanın içeriğini sanki doğrudan yazılmış gibi dahil eder.

---

## Memory Sistemi

Claude Code'un kalıcı belleği `~/.claude/projects/` altında proje başına saklanır.

**Manuel kaydetme:**
```
"Bunu hatırla: Bu projede migration'lar schema/ altında yaşıyor."
```

**Ne zaman kullanılır:**
- Her konuşmada tekrarladığın bilgiler
- CLAUDE.md'ye koymak istemediğin kişisel tercihler

---

## PROJECT_CONTEXT ve SESSION_CONTEXT ile Bağlam Katmanlama

CLAUDE.md tek dosyada şişmeye başlarsa kalıcı ve geçici bağlamı ayır:

| Dosya | Ne içerir | Ne sıklıkla değişir |
|---|---|---|
| `CLAUDE.md` | Davranış kuralları, yasaklar, komutlar | Nadiren |
| `PROJECT_CONTEXT.md` | Mimari kararlar, teknoloji seçimleri, önemli bağlam | Ayda birkaç kez |
| `SESSION_CONTEXT.md` | Süren iş, açık kararlar, geçici notlar | Her oturumda |

**CLAUDE.md içine import et:**

```markdown
@./PROJECT_CONTEXT.md
@./SESSION_CONTEXT.md
```

**SESSION_CONTEXT.md örneği:**

```markdown
# Oturum Bağlamı

## Süren İş
- Payment modülü yarım kaldı — src/payment/webhook.ts

## Açık Kararlar
- Retry stratejisi: exponential backoff mı, sabit aralık mı?

## Sonraki Adım
- Webhook testlerini yaz
```

Her yeni konuşma başında Claude bu dosyayı okur ve tam olarak kaldığın yerden devam eder. Oturum tamamlandığında SESSION_CONTEXT.md'yi güncelle.

---

## İzin Yönetimi

`~/.claude/settings.json` veya `.claude/settings.json`:

```json
{
  "permissions": {
    "allow": [
      "Bash(npm run *)",
      "Bash(git *)",
      "Edit(src/**)"
    ],
    "deny": [
      "Bash(rm -rf *)"
    ]
  }
}
```

→ Detaylar için: [settings.json](../03-hooks-otomasyon/01-settings-json.md)

---

## → Sonraki Adım

CLAUDE.md'yi kurduysun, tekrarlayan işleri otomatikleştir:

**[03 › Hooks & Otomasyon](../03-hooks-otomasyon/README.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| @import çalışmıyor | [Temel Yapı — Dosya Konumu](./01-temel-yapi.md#dosya-konumu) |
| İzin verdiğim komut hâlâ soruluyor | [settings.json](../03-hooks-otomasyon/01-settings-json.md) |
| Memory'e kaydettiğim şey unutuldu | [Bağlam Yönetimi](../05-prompt-stratejileri/02-baglam-yonetimi.md) |
