# Senaryo 05 › Performans Optimizasyonu

**Durum:** Uygulama yavaşlamaya başladı. Kullanıcılar şikayet ediyor ama sorun nerede belli değil.

**Zorluk:** 🟡 Orta  
**Kural:** Ölçmeden optimize etme.

---

## Adım 1 — Önce Ölç, Sonra Yorumla

```
"Bu uygulamada performans sorunları yaşıyoruz.
 Önce hangi metrikleri ölçmem gerektiğini ve
 nasıl ölçeceğimi anlat. Henüz kod değiştirme."
```

---

## Adım 2 — Bottleneck Tespiti

Profiling çıktısını veya yavaş sorgu logunu Claude'a ver:

```
"Bu profiling çıktısını analiz et:
 [çıktı]

 En çok zaman harcanan 3 alanı listele.
 Her biri için kök neden tahmini yap."
```

Veya yavaş API endpoint varsa:

```
"Bu endpoint neden yavaş olabilir?
 [endpoint kodu]
 Veritabanı sorguları, N+1 problemi, gereksiz hesaplama açısından bak."
```

---

## Adım 3 — Tek Değişiklik, Tek Ölçüm

Her optimizasyonu izole et:

```
"Şu N+1 sorunu için en minimal düzeltmeyi öner.
 Başka şeye dokunma — sadece bu sorunu çöz.
 Önce ve sonra nasıl ölçeceğimi de belirt."
```

---

## Adım 4 — Veritabanı Optimizasyonu

```
"Bu sorguyu analiz et:
 [SQL veya ORM kodu]

 Index eklemek, sorguyu yeniden yazmak veya
 eager loading kullanmak seçeneklerini karşılaştır."
```

---

## Adım 5 — Frontend Performansı

```
"Bu bileşen her render'da [işlem] yapıyor.
 useMemo / useCallback kullanımı burada uygun mu?
 Trade-off'ları açıkla."
```

---

## Bu Senaryoda Sık Yapılan Hatalar

| Hata | Sonucu |
|---|---|
| Ölçmeden optimize etmek | Yanlış yeri optimize edersin |
| Birden fazla şeyi aynı anda değiştirmek | Hangisinin fark yarattığını bilemezsin |
| Micro-optimizasyon takıntısı | Gerçek bottleneck'i kaçırırsın |
| Cache ekleyip sorunu örtmek | Kök neden çözülmez, birikerek büyür |

---

## → Sonraki Adım

**[Senaryo 06 › Güvenlik Denetimi](./06-guvenlik-denetimi.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Profiling nasıl yapılır bilmiyorum | [Test & Debug](../01-gelistirme-sureci/03-test-ve-debug.md) |
| Optimizasyon sonrası testler bozuldu | [Test & Debug](../01-gelistirme-sureci/03-test-ve-debug.md) |
| Claude çok büyük değişiklik önerdi | [Yaygın Hatalar](../05-prompt-stratejileri/03-yaygin-hatalar.md) |
