# 03 › Hooks & Otomasyon

Claude Code'un belirli eylemlerinden önce veya sonra otomatik komutlar çalıştır.

---

## Hook Nedir?

Claude bir araç çağırmadan önce veya sonra, senin belirlediğin bir shell komutu çalışır. Böylece:
- Her kayıtta lint çalıştırabilirsin
- Tehlikeli komutları engelleyebilirsin
- Bildirim gönderebilirsin

---

## Bölümler

| Konu | Dosya |
|---|---|
| settings.json yapısı ve konumu | [settings.json](./01-settings-json.md) |
| PreToolUse, PostToolUse ve diğer hook tipleri | [Hook Tipleri](./02-hook-tipleri.md) |
| Hazır kullanılabilir tarifler | [Tarifler](./03-tarifler.md) |

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Hook hiç tetiklenmiyor | [settings.json — Konum](./01-settings-json.md#konum-ve-format) |
| Yanlış hook tipi kullandım | [Hook Tipleri](./02-hook-tipleri.md) |
| Ajan kullanmak istiyorum | [Ajanlar](../04-ajanlar/README.md) |
