# Senaryo 04 › Yeni Özellik Ekleme

**Durum:** Çalışan bir projeye yeni bir özellik ekleyeceksin. Mevcut kodu bozmadan, test coverage'ı düşürmeden.

**Zorluk:** 🟡 Orta

---

## Adım 1 — Mevcut Kodu Anla

Özelliği yazmadan önce Claude'a ilgili alanı okut:

```
"Şu dosyaları oku: [ilgili dosyalar]
 Yeni bir [özellik adı] ekleyeceğim.
 Mevcut pattern'leri öğren, henüz bir şey yazma."
```

---

## Adım 2 — Etki Alanını Belirle

```
"[özellik açıklaması] eklemek istiyorum.
 Hangi mevcut dosyalar etkilenir?
 Yeni hangi dosyalar gerekir?
 Listele, uygulamaya başlama."
```

---

## Adım 3 — Plan Modu ile Onayla

```
"/plan

 Mevcut [ilgili modül] yapısına uygun şekilde [özellik] ekle.
 Kısıtlar:
 - Mevcut API contract'ı bozma
 - Yeni bağımlılık ekleme
 - Test coverage %80 altına düşürme"
```

Planı incele, gerekirse düzelt, onayla.

---

## Adım 4 — Önce Test, Sonra Kod

Test-driven yaklaşım Claude ile kolaylaşır:

```
"Önce [özellik] için başarısız testler yaz.
 Sonra bu testleri geçirecek implementasyonu yaz."
```

---

## Adım 5 — Regresyon Kontrolü

Özelliği yazdıktan sonra:

```
"Yaptığın değişiklikler mevcut testleri kırar mı?
 Tüm test dosyalarını tara ve riskli alanları listele."
```

---

## Adım 6 — Code Review

```
"/review

 Ekledim: [özellik özeti]
 Değiştirilen dosyalar: [liste]
 Özellikle şuna bak: [kritik alan]"
```

---

## Bu Senaryoda Sık Yapılan Hatalar

| Hata | Sonucu |
|---|---|
| Mevcut kodu okumadan yazmak | Claude projenin pattern'lerine uymayan kod üretir |
| "Ekle ve test et" yerine "her şeyi değiştir" | Regresyon riski artar |
| Test yazmadan merge etmek | İlerleyen sprinte bozuk özellik taşınır |

---

## → Sonraki Adım

**[Senaryo 05 › Performans Optimizasyonu](./05-performans-optimizasyonu.tr.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Plan modu nasıl kullanılır | [Plan Modu](../05-prompt-stratejileri/01-plan-modu.tr.md) |
| Test yazmayı bilmiyorum | [Test & Debug](../01-gelistirme-sureci/03-test-ve-debug.tr.md) |
| Code review nasıl yapılır | [Code Review](../01-gelistirme-sureci/04-code-review.tr.md) |
| Mevcut kodu bozduk | [Yaygın Hatalar](../05-prompt-stratejileri/03-yaygin-hatalar.tr.md) |
