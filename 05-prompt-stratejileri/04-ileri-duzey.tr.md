# 05 › Prompt Stratejileri › İleri Düzey

## /think Komutu

Karmaşık bir karar için Claude'u daha derin düşünmeye zorla:

```
/think

"Bu migration stratejisinin olası yan etkilerini listele."
```

ya da metin içinde:

```
"Düşün: Bu değişiklik hangi edge case'leri kırabilir?"
```

---

## Çıktı Formatını Belirle

Claude'un belirli bir formatta çıktı üretmesini iste:

```
"Analiz sonucunu şu formatta döndür:
 - Sorun: [ne]
 - Neden: [kök neden]
 - Çözüm: [önerilen adımlar]
 - Risk: [varsa yan etkiler]"
```

---

## Rol Belirleme

Prompt'un başında bağlam ver:

```
"Senior backend developer olarak bu API tasarımını incele.
 Performans ve güvenlik açısından değerlendir."
```

---

## Adım Adım Onay

Her adımı ayrı onayla:

```
"Her adımı tamamladıktan sonra dur ve benim onayımı bekle.
 Onaylamadan sonraki adıma geçme."
```

---

## /compact ile Sıkıştırma

Uzun konuşmalarda bağlamı temizler:

```
/compact
```

Önemli kararlar kaybolmasın diye önce CLAUDE.md'ye not al.

---

## → Sonraki Adım

Tüm bölümleri tamamladıysan başa dön ve eksik kaldığın noktayı seç:

**[Ana Navigasyon](../README.tr.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| /think yeterince derin düşünmedi | Soruyu daha spesifik sor |
| Adım adım onay çalışmıyor | Plan modunu dene → [Plan Modu](./01-plan-modu.tr.md) |
| Bağlam kaybı yaşıyorum | [Bağlam Yönetimi](./02-baglam-yonetimi.tr.md) |
| Ana sayfaya dönmek istiyorum | [Navigasyon Ağacı](../README.tr.md) |
