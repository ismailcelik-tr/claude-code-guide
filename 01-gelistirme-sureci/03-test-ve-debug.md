# 01 › Geliştirme Süreci › Test & Debug

Test yazma ve hata ayıklama sürecinde Claude Code kullanımı.

---

## Test Üretme

```
"src/utils/parser.ts için unit testler yaz.
 Edge case'leri kapsa: boş input, null, maksimum uzunluk."
```

Mevcut test dosyası varsa önce onu okut:

```
"Mevcut test stilini test/utils/ klasöründen öğren,
 aynı stilde parser.test.ts yaz."
```

---

## Hata Ayıklama

Hata mesajını olduğu gibi yapıştır:

```
"Şu hatayı alıyorum:
 TypeError: Cannot read properties of undefined (reading 'map')
 at src/components/UserList.tsx:42

 İlgili dosyayı oku ve nedenini bul."
```

Claude; dosyayı okur, satırı bulur, kök nedeni açıklar ve düzeltir.

---

## Log Analizi

Uzun log çıktılarını doğrudan yapıştırabilirsin:

```
"Bu CI logunu analiz et ve başarısızlık nedenini listele:"
[log içeriği]
```

---

## Testler Geçiyor Ama Üretim Patlıyor

Bu genellikle mock/gerçek ortam farkından kaynaklanır.

1. Test ortamında mock'lanan şeyi bul
2. Claude'a gerçek ortam farkını açıkla
3. Entegrasyon testi yaz

```
"Bu test mock database kullanıyor.
 Gerçek Postgres bağlantısıyla çalışan bir entegrasyon testi yaz."
```

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Test üretildi ama çalışmıyor | [Geliştirme — Mevcut Kod Okuma](./02-gelistirme.md) |
| Hata mesajı anlaşılmıyor | [Yaygın Hatalar](../05-prompt-stratejileri/03-yaygin-hatalar.md) |
| Testler geçiyor ama production'da patlıyor | Bu sayfanın "Mock/Gerçek" bölümü |
| Code review'a geçmek istiyorum | [Code Review](./04-code-review.md) |
