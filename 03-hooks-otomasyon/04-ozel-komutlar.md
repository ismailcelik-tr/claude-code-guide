# 03 › Hooks & Otomasyon › Özel Komutlar

Aynı prompt'u üç kereden fazla yazdıysan onu bir slash komutuna dönüştür.

---

## Özel Komut Nedir?

`.claude/commands/` dizinine koyduğun Markdown dosyalarıdır. Claude Code onları `/komut-adi` şeklinde slash komutu olarak tanır.

```
proje/
└── .claude/
    └── commands/
        ├── review.md
        ├── deploy-check.md
        └── sprint-summary.md
```

---

## İlk Komutu Yaz

**`.claude/commands/review.md`:**

```markdown
Mevcut branch'teki değişiklikleri incele.

Şunları kontrol et:
1. Güvenlik açığı var mı?
2. Test eksik mi?
3. CLAUDE.md kurallarına uyuluyor mu?

Her bulgu için: dosya yolu, satır numarası, öneri.
```

Artık her PR öncesi `/review` yazmak yeterli.

---

## Kullanışlı Komut Örnekleri

### Deploy Kontrol Listesi

**`.claude/commands/deploy-check.md`:**

```markdown
Deploy öncesi kontrol listesi oluştur.

Şunları doğrula:
- [ ] Tüm testler geçiyor
- [ ] .env.example güncel
- [ ] Migration'lar hazır
- [ ] CHANGELOG.md güncellendi

Eksik olan maddeleri listele.
```

### Sprint Özeti

**`.claude/commands/sprint-summary.md`:**

```markdown
Son commit'leri oku ve bu sprint'te yapılanları özetle.

Format:
## Tamamlananlar
## Devam Edenler
## Bilinen Sorunlar
```

### Hızlı Debug

**`.claude/commands/debug.md`:**

```markdown
Şu hatayı analiz et: $ARGUMENTS

1. Kök nedeni belirle
2. İlgili dosyaları oku
3. Minimum değişiklikle düzeltmeyi öner
```

`$ARGUMENTS` ile komuta parametre geçebilirsin:

```
/debug "TypeError: Cannot read properties of undefined"
```

---

## Ne Zaman Komut Yazmalısın?

| Durum | Yap |
|---|---|
| Aynı prompt'u 3+ kez yazdın | Komuta dönüştür |
| Takımda herkes aynı süreci uygulayacak | Komuta dönüştür |
| Bir kerelik görev | Doğrudan prompt yaz |
| Bağlama çok özgü | Doğrudan prompt yaz |

---

## → Sonraki Adım

Otomasyonu tamamladıysan ajan kullanımına geç:

**[04 › Ajanlar](../04-ajanlar/README.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Komut tanınmıyor | `.claude/commands/` dizininin proje kökünde olduğunu kontrol et |
| $ARGUMENTS çalışmıyor | Komut dosyasında `$ARGUMENTS` ibaresini aynen kullan |
| Hook mu komut mu kullanacağımı bilemedim | Hook otomatik tetiklenir, komut manuel çağrılır |
| settings.json nereye gider | [settings.json](./01-settings-json.md#konum-ve-format) |
