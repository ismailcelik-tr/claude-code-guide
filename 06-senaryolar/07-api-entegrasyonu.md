# Senaryo 07 › API Entegrasyonu

**Durum:** Üçüncü taraf bir API'yi uygulamana bağlayacaksın — ödeme, bildirim, harita, sosyal medya veya başka bir servis.

**Zorluk:** 🟢 Başlangıç

---

## Adım 1 — API'yi Anla

Dokümantasyonu veya OpenAPI spec'i Claude'a ver:

```
"Bu API dokümantasyonunu oku:
 [URL veya içerik]

 Şunları özetle:
 - Auth yöntemi (API key, OAuth, Bearer)
 - Kullanacağım endpoint'ler
 - Rate limit kuralları
 - Hata kodları ve anlamları"
```

---

## Adım 2 — Entegrasyon Katmanı Tasarla

```
"Bu API için bir servis katmanı tasarla.
 Mevcut proje yapısı: [dizin yapısı]

 Şunları sağla:
 - API key'i environment variable'dan oku
 - Her endpoint için ayrı fonksiyon
 - Hata yönetimi merkezi olsun
 - Retry mantığı ekle"
```

---

## Adım 3 — Mock ile Geliştir

Gerçek API'ye bağlanmadan önce mock kullan:

```
"Bu API'nin şu endpoint'lerini mock'la:
 [endpoint listesi]

 Test ortamında gerçek API'ye istek atmadan
 entegrasyonu test edebileyim."
```

---

## Adım 4 — Hata Yönetimi

```
"Bu API şu hata kodlarını dönebilir:
 [hata kodları]

 Her biri için uygulamam nasıl davranmalı?
 Kullanıcıya ne göstermeli, loglama nasıl olmalı?"
```

---

## Adım 5 — Gerçek Ortamda Test

Mock'tan gerçek API'ye geçerken:

```
"Entegrasyonu production'a almadan önce
 kontrol listesi oluştur.
 API key yönetimi, rate limit takibi,
 fallback senaryoları dahil olsun."
```

---

## Bu Senaryoda Sık Yapılan Hatalar

| Hata | Sonucu |
|---|---|
| API key'i doğrudan koda yazmak | Secret ifşası riski |
| Mock yazmadan geliştirmek | Her testte gerçek API'ye istek atılır, rate limit aşılır |
| Hata yönetimi atlamak | API down olduğunda uygulama çöker |
| Rate limit'i göz ardı etmek | Production'da aniden servis kesilir |

---

## → Sonraki Adım

**[Senaryo 08 › Database Migrasyonu](./08-database-migrasyonu.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| API entegrasyonu test edilemiyor | [Test & Debug](../01-gelistirme-sureci/03-test-ve-debug.md) |
| Environment variable yönetimi | [Deployment — Ortam Değişkenleri](../01-gelistirme-sureci/05-deployment.md) |
| CLAUDE.md'ye API bilgisi eklemek | [CLAUDE.md Proje Özeli](../02-claude-md/02-proje-ozeli.md) |
