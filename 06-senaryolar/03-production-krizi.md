# Senaryo 03 › Production Krizi

**Durum:** Canlı sistemde bir şeyler patlıyor. Kullanıcılar etkileniyor, her dakika önemli.

**Zorluk:** 🔴 İleri  
**Öncelik:** Önce sistemi ayağa kaldır, sonra kök nedeni bul

---

## Kriz Anında Claude'u Nasıl Kullanırsın?

Panikle uzun açıklamalar yazma. Kısa, net, odaklı ol.

---

## Adım 1 — Hatayı Hızlıca İzole Et

Error log'u veya stack trace'i doğrudan yapıştır:

```
"Production'da şu hata var:
 [hata mesajı / stack trace]

 Önce sadece kök nedeni belirle. Düzeltme önerme henüz."
```

Claude kök nedeni açıklarsa devam et:

```
"Tamam. Şimdi en az riskli düzeltmeyi öner.
 Minimal değişiklik — başka şeyi bozma."
```

---

## Adım 2 — Log Analizi

CI/CD veya uygulama logunu yapıştır:

```
"Bu production logunu analiz et.
 Hata başladığı anı bul ve öncesinde ne değişti?"
[log içeriği]
```

---

## Adım 3 — Hızlı Düzeltme (Hotfix)

```
"Şu dosyayı oku: [dosya yolu]
 Minimum değişiklikle [sorun] düzelt.
 Yeni bir şey ekleme, sadece kır olanı onar."
```

> [!CAUTION]
> Kriz anında büyük refactor yapmaya kalkma. Önce sistemi çalışır hale getir.

---

## Adım 4 — Değişikliği Doğrula

Düzeltmeyi deploy etmeden önce:

```
"Yaptığın değişikliği özetle:
 - Ne değişti
 - Yan etkisi olabilir mi
 - Nasıl doğrularım"
```

---

## Adım 5 — Kriz Sonrası Analiz

Sistem stabilize olduktan sonra:

```
"Bu production krizinin neden olduğunu analiz et.
 Bir daha olmaması için ne yapılabilir?
 Test, monitoring veya kod açısından öner."
```

---

## Kriz Anında Kaçınılacaklar

| Yapma | Neden |
|---|---|
| "Her şeyi yeniden yaz" demek | Kriz anında büyük değişiklik yeni krizler doğurur |
| Birden fazla düzeltmeyi aynı anda deploy etmek | Hangisinin işe yaradığını bilemezsin |
| Düzeltmeyi test etmeden push etmek | İkinci bir krizi tetikleyebilirsin |
| Claude'a secret/API key yapıştırmak | Güvenlik riski — sadece değişken adlarını paylaş |

---

## → Sonraki Adım

Kriz yönetimini öğrendiysen, sıfır regresyonla özellik eklemeyi gör:

**[Senaryo 04 › Yeni Özellik Ekleme](./04-yeni-ozellik.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Log analizi nasıl yapılır | [Test & Debug — Log Analizi](../01-gelistirme-sureci/03-test-ve-debug.md) |
| Deployment sürecinde sorun | [Deployment](../01-gelistirme-sureci/05-deployment.md) |
| Claude çok büyük değişiklik önerdi | [Yaygın Hatalar](../05-prompt-stratejileri/03-yaygin-hatalar.md) |
