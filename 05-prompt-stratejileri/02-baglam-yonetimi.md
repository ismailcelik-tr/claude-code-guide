# 05 › Prompt Stratejileri › Bağlam Yönetimi

## Bağlam Nedir?

Claude'un "hafızası" bir konuşma içinde tuttuğu tüm mesajlardır. Konuşma uzadıkça bağlam dolmaya başlar.

---

## Bağlam Dolduğunda Ne Olur?

- Eski mesajlar özetlenir veya silinir
- Claude önceki kararları "unutabilir"
- Performans düşebilir

---

## Bağlamı Verimli Kullan

**Gereksiz şeyleri konuşmaya ekleme:**
- Uzun dosya içeriklerini manuel yapıştırma — Claude'a dosyayı okumasını söyle
- Tekrarlayan talimatları her mesajda yazma — CLAUDE.md'ye taşı

**Sık kullanılan bağlamı CLAUDE.md'ye taşı:**
```markdown
## Mimari Kararlar
- Tüm API çağrıları src/api/client.ts üzerinden geçer
```

---

## Konuşmayı Temizle

Bağlam çok dolduğunda yeni bir konuşma başlat ve önemli bağlamı özetle:

```
"Önceki konuşmamızda şunları yaptık: [özet].
 Şimdi şunu yapmak istiyorum: [yeni görev]."
```

---

## /compact Komutu

```
/compact
```

Konuşma geçmişini sıkıştırır, bağlamı temizler ama bilgiyi korur.

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Claude önceki kararı unuttu | CLAUDE.md'ye taşı veya yeni konuşmada özetle |
| Konuşma çok yavaşladı | /compact çalıştır |
| Memory sistemi nedir | [CLAUDE.md İleri Düzey](../02-claude-md/03-ileri-duzey.md) |
