# 04 › Ajanlar › Paralel Çalıştırma

## Ne Zaman Paralel? {#ne-zaman-paralel}

İki görev **birbirinin sonucuna bağlı değilse** paralel çalıştır.

**Paralel uygun:**
- "Frontend ve backend testlerini aynı anda çalıştır"
- "Bu iki bağımsız modülü ayrı ajan ile incele"

**Sıralı gerekir:**
- "Önce araştır, sonra uygulamaya başla"
- "A'nın sonucuna göre B'yi yap"

---

## Paralel Ajan Çalıştırma

Claude Code'a birden fazla ajan için tek mesajda talimat ver:

```
"Şu iki görevi paralel çalıştır:
 1. Explore ile src/api/ dizinindeki tüm endpoint'leri listele
 2. Explore ile src/components/ dizinindeki tüm bileşenleri listele"
```

---

## Arkaplanda (Background) Çalıştırma

Sonucu hemen gerekmiyorsa:

```
"Bu araştırmayı arka planda çalıştır, bitince haber ver.
 [görev açıklaması]"
```

---

## Paralelin Maliyeti

Her ajan bağımsız bir Claude örneğidir — token maliyeti katlanır. Sadece gerçekten bağımsız görevlerde kullan.

---

## → Sonraki Adım

Ajanları öğrendiysen prompt stratejilerine geç:

**[05 › Prompt Stratejileri](../05-prompt-stratejileri/README.tr.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Ajanlar birbirinin işini bozdu | Görevler gerçekten bağımsız değil — sıraya al |
| Ajan sonucu bekliyorum ama bitmiyor | Arka plan ajanı olabilir — konuşmaya devam et, bildirim gelir |
| Agent tool nedir bilmiyorum | [Agent Tool Temel](./01-agent-tool.tr.md) |
