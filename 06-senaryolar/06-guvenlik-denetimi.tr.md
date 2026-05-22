# Senaryo 06 › Güvenlik Denetimi

**Durum:** Kod tabanını güvenlik açısından taramak istiyorsun — deploy öncesi, periyodik denetim veya bir olay sonrası.

**Zorluk:** 🔴 İleri  
**Kural:** Güvenlik bulguları kamuya açılmadan önce düzeltilmeli.

---

## Adım 1 — Bağımlılık Taraması

```
"package.json ve package-lock.json dosyalarını oku.
 Bilinen güvenlik açığı olan bağımlılıkları listele.
 Her biri için: açık seviyesi, etkilenen versiyon, güvenli versiyon."
```

---

## Adım 2 — Kod Analizi

Kritik dosyaları Claude'a incelet:

```
"Şu dosyaları güvenlik açısından incele:
 [dosya listesi]

 Şunlara bak:
 - SQL injection / NoSQL injection
 - XSS riski
 - Kimlik doğrulama atlaması
 - Hassas veri ifşası
 - Güvensiz doğrudan nesne referansı (IDOR)

 Her bulgu için: dosya, satır, risk seviyesi, düzeltme önerisi."
```

---

## Adım 3 — Authentication & Authorization Kontrolü

```
"Auth middleware'ini oku.
 Şunları kontrol et:
 - Token doğrulama eksiksiz mi?
 - Yetki kontrolü her endpoint'te var mı?
 - Oturum süresi doğru ayarlanmış mı?"
```

---

## Adım 4 — Güvenlik Açığı Düzeltme

Bulgular netleştikten sonra sırayla düzelt:

```
"Önce yüksek riskli bulgulardan başla.
 Her düzeltme için:
 1. Minimal kod değişikliği yap
 2. Düzeltmenin ne işe yaradığını açıkla
 3. Regresyon testi yaz"
```

---

## Adım 5 — Secret Taraması

```
"Kod tabanında hardcode edilmiş secret, API key veya
 şifre olup olmadığını tara.
 .env dosyalarına bakma — sadece kaynak koda bak."
```

> [!CAUTION]
> Gerçek secret değerlerini Claude'a yapıştırma. Sadece değişken adlarını ve dosya konumlarını paylaş.

---

## Bu Senaryoda Sık Yapılan Hatalar

| Hata | Sonucu |
|---|---|
| Sadece bağımlılıkları tarayıp kodu atlamak | Uygulama katmanındaki açıklar görünmez |
| Bulguları önceliklendirmeden hepsini aynı anda düzeltmek | Kritik açıklar beklerken düşük risk olanlarla zaman kaybedilir |
| Secret'ı Claude'a yapıştırmak | Güvenlik riski |
| Düzeltme sonrası test yazmamak | Açık ilerleyen PR'da yeniden açılabilir |

---

## → Sonraki Adım

**[Senaryo 07 › API Entegrasyonu](./07-api-entegrasyonu.tr.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Güvenlik bulgusunu nasıl düzelteceğimi bilemedim | [Geliştirme](../01-gelistirme-sureci/02-gelistirme.tr.md) |
| Test nasıl yazılır | [Test & Debug](../01-gelistirme-sureci/03-test-ve-debug.tr.md) |
| Güvenlik bildirimi yapmak istiyorum | [SECURITY.md](../SECURITY.tr.md) |
