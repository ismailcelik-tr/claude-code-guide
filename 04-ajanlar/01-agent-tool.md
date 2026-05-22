# 04 › Ajanlar › Agent Tool

## Agent Tool Nedir?

Claude Code, karmaşık görevleri başka bir Claude örneğine devredebilir. Bu alt ajan; kendi araç seti, bağlamı ve izinleriyle çalışır.

---

## Ne Zaman Kullanılır?

**Kullan:**
- Kod tabanının tamamını tarayan araştırma görevleri
- Ana konuşmayı şişirmeden derin analiz
- Bağımsız, paralel çalışabilecek alt görevler

**Kullanma:**
- Tek satırlık düzeltmeler
- Birbirini bekleyen sıralı görevler
- Kullanıcıyla doğrudan etkileşim gerektiren işler

---

## Temel Kullanım

Claude'a açıkça söyle:

```
"Explore subagent'i kullanarak src/ dizinindeki tüm API endpoint'lerini listele.
 Dosya yolu ve HTTP metodu formatında döndür."
```

---

## İyi Ajan Promptu Nasıl Yazılır?

Ajan bir önceki konuşmayı **görmez**. Prompt'u kendi kendine anlaşılır yaz:

```
"Şu görev için araştırma yapıyorsun:
 [Bağlam: ne incelenecek]
 [Hedef: ne bulunacak]
 [Format: nasıl döndürülecek]"
```

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Ajan yanlış sonuç döndürdü | Prompt'u bağımsız yaz — önceki konuşmayı bilmiyor |
| Hangi subagent tipi kullanacağımı bilemedim | [Subagent Tipleri](./02-subagent-tipleri.md) |
| Paralel çalıştırmak istiyorum | [Paralel Çalıştırma](./03-paralel-calistirma.md) |
