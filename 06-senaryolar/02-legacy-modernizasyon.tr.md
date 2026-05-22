# Senaryo 02 › Legacy Modernizasyon

**Durum:** Yıllardır dokunulmamış bir kod tabanı var. Test yok, dokümantasyon yok, TypeScript yok. Bunu adım adım modernize edeceksin.

**Zorluk:** 🟡 Orta  
**Risk:** Yüksek — mevcut sistemi bozma ihtimali var

---

## Altın Kural

> Tüm kodu bir anda değiştirme. Her adımda sistemi çalışır durumda tut.

---

## Adım 1 — Kod Tabanını Tanı

Claude'a önce okuma görevi ver, değişiklik yok:

```
"src/ dizinini incele. Şunları bul ve listele:
 1. En kritik dosyalar (sık referans verilenler)
 2. Açık güvenlik riskleri
 3. En büyük teknik borç alanları
 Hiçbir şeyi değiştirme, sadece rapor et."
```

Explore subagent kullanmak daha güvenli:

```
"Explore subagent kullanarak src/ dizinini analiz et.
 Dosya bağımlılık haritasını çıkar."
```

---

## Adım 2 — CLAUDE.md'yi Mevcut Duruma Göre Yaz

```
"Şu dizin yapısını ve package.json'ı oku.
 Bu legacy projeyi tanımlayan bir CLAUDE.md oluştur.
 Özellikle şunları belirt:
 - Dokunulmaması gereken dosyalar (src/legacy/)
 - Mevcut naming convention'lar
 - Bilinen kırık bölümler"
```

---

## Adım 3 — Test Koruması Kur

Değişiklik yapmadan önce mevcut davranışı testlerle sabitle:

```
"src/core/payment.js dosyasını oku.
 Bu dosyanın mevcut davranışını belgeleyen karakterizasyon testleri yaz.
 Testi geçirmeyi değil, mevcut çıktıyı belgelemeyi hedefle."
```

---

## Adım 4 — Küçük Parçalar Halinde Modernize Et

Her dosya veya modül için ayrı oturum aç:

```
"Sadece src/utils/date.js dosyasını modernize et:
 1. ES modules'e geçir
 2. JSDoc ekle
 3. Mevcut testleri geçirmeye devam et
 Başka dosyaya dokunma."
```

---

## Adım 5 — TypeScript Geçişi (isteğe bağlı)

En az riskli dosyadan başla:

```
"src/utils/date.js dosyasını TypeScript'e geçir.
 any tipi kullanma.
 Diğer dosyalardaki import'ları güncelle ama başka şeye dokunma."
```

---

## Adım 6 — Her Adımda Doğrula

```
"Yaptığın değişikliklerden sonra testleri çalıştır.
 Başarısız test varsa önce onu düzelt, ileriye geçme."
```

---

## Bu Senaryoda Sık Yapılan Hatalar

| Hata | Sonucu |
|---|---|
| Test yazmadan refactor etmek | Neyi bozduğunu bilemezsin |
| Birden fazla dosyayı aynı anda değiştirmek | Hata kaynağını izole edemezsin |
| `any` tipiyle TypeScript'e geçmek | Tip güvenliği kazanmamış olursun |
| `src/legacy/` gibi bölgelere izinsiz girmek | Başka sistemler bağımlıysa çöker |

---

## → Sonraki Adım

Modernizasyon tamamsa, production krizlerini yönetmeyi öğren:

**[Senaryo 03 › Production Krizi](./03-production-krizi.tr.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Explore subagent nasıl kullanılır | [Subagent Tipleri](../04-ajanlar/02-subagent-tipleri.tr.md) |
| Testler nasıl üretilir | [Test & Debug](../01-gelistirme-sureci/03-test-ve-debug.tr.md) |
| Claude dokunmaması gereken dosyayı değiştirdi | [CLAUDE.md Kısıtlar](../02-claude-md/02-proje-ozeli.tr.md) |
