# 05 › Prompt Stratejileri › Plan Modu

## Plan Modu Nedir?

Claude uygulamaya başlamadan önce ne yapacağını sana gösterir ve onayını bekler.

---

## Nasıl Etkinleştirilir

```
/plan
```

ya da doğal dil ile:

```
"Uygulamaya başlamadan önce planını göster, onaylayayım."
```

---

## Plan Modunda Claude Ne Yapar?

1. Kod tabanını okur, araştırır
2. Yaklaşım seçenekleri sunar (gerekirse)
3. Adım adım planı yazar
4. **Senin onayını bekler**
5. Onaydan sonra uygulamaya başlar

---

## Planı Görünce Ne Yapmalısın?

- **Onaylamak için:** "Devam et" veya "Başla"
- **Değiştirmek için:** "3. adımı değiştir, X yerine Y yap"
- **İptal için:** "Dur, farklı bir yaklaşım deneyelim"

---

## Ne Zaman Kullanılır?

| Görev | Plan Modu? |
|---|---|
| Birden fazla dosyayı etkileyen değişiklik | Evet |
| Mimari karar gerektiren özellik | Evet |
| Tek satır düzeltme | Hayır |
| Açık ve net görev | İsteğe bağlı |

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Plan modu aktif ama Claude uygulamaya başladı | Onay vermeden "devam" dedin mi? |
| Plan çok detaylı / yüzeysel kaldı | [İleri Düzey — Prompt Teknikleri](./04-ileri-duzey.md) |
| Planlama aşamasına geri dönmek istiyorum | [Geliştirme Süreci — Planlama](../01-gelistirme-sureci/01-planlama.md) |
