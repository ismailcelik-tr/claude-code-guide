# Senaryo 08 › Database Migrasyonu

**Durum:** Veritabanı şemasını değiştirmen gerekiyor — yeni kolon, tablo yeniden yapılandırma veya büyük veri taşıma. Sistem çalışmaya devam edecek.

**Zorluk:** 🔴 İleri  
**Kural:** Her migration geri alınabilir olmalı.

---

## Adım 1 — Değişikliği Analiz Et

```
"Şu migration'ı yapmam gerekiyor: [açıklama]
 Mevcut şema: [şema veya model dosyası]

 Şunları listele:
 - Etkilenen tablolar ve kolonlar
 - Veri kaybı riski var mı?
 - Zero-downtime için ne gerekiyor?
 - Geri alma (rollback) planı nedir?"
```

---

## Adım 2 — Expand-Contract Stratejisi

Büyük şema değişiklikleri için zero-downtime yaklaşımı:

```
"Bu migration'ı expand-contract pattern ile nasıl yaparım?
 Mevcut kolon: [eski kolon]
 Hedef: [yeni yapı]

 Adım adım plan yap — her adım bağımsız deploy edilebilir olsun."
```

**Expand-contract nedir:**
1. **Expand** — yeni yapıyı eski yanına ekle, her ikisini de yaz
2. **Migrate** — mevcut veriyi yeni yapıya taşı
3. **Contract** — eski yapıyı kaldır

---

## Adım 3 — Migration Dosyasını Yaz

```
"Şu migration'ı [Prisma / Flyway / Alembic / ActiveRecord] ile yaz:
 [değişiklik açıklaması]

 Up ve down migration'larını birlikte yaz.
 Büyük tablolar için batch işleme ekle."
```

---

## Adım 4 — Veri Doğrulama

Migration sonrası veri bütünlüğünü kontrol et:

```
"Bu migration'dan sonra veri bütünlüğünü doğrulayacak
 sorgular yaz.
 Eksik veri, null kırılmaları veya constraint ihlali
 olup olmadığını kontrol etsin."
```

---

## Adım 5 — Rollback Planı

```
"Bu migration başarısız olursa geri alma planını yaz.
 Hangi adımda ne yapılır?
 Veri kaybı olmadan nasıl geri dönülür?"
```

> [!CAUTION]
> Production migration'ı öncesinde mutlaka staging ortamında test et ve veritabanı yedeği al.

---

## Bu Senaryoda Sık Yapılan Hatalar

| Hata | Sonucu |
|---|---|
| Yedek almadan migration çalıştırmak | Veri kaybı geri dönüşsüz olabilir |
| Down migration yazmamak | Rollback imkansız hale gelir |
| Büyük tabloda kilit almak | Production'da servis kesintisi |
| Staging'de test etmemek | Production'da ilk kez karşılaşılan sorunlar |

---

## → Sonraki Adım

Tüm senaryoları tamamladıysan, hızlı başvuru kartına bak:

**[Hızlı Başvuru Kartı](../cheatsheet.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Migration sonrası production patlıyor | [Production Krizi](./03-production-krizi.md) |
| Test ortamında çalışıyor, prod'da çalışmıyor | [Deployment](../01-gelistirme-sureci/05-deployment.md) |
| Migration'ı nasıl test edeceğimi bilemedim | [Test & Debug](../01-gelistirme-sureci/03-test-ve-debug.md) |
