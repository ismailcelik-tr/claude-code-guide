# 05 › Prompt Stratejileri › Yaygın Hatalar

## Hata 1: Belirsiz Görev

**Yanlış:**
```
"Auth sistemini iyileştir."
```

**Doğru:**
```
"src/auth/middleware.ts'deki token doğrulama fonksiyonuna
 expiry kontrolü ekle. Süresi dolmuş token için 401 dön."
```

---

## Hata 2: Fazla Büyük Görev

**Yanlış:**
```
"Tüm uygulamayı TypeScript'e geçir."
```

**Doğru:**
```
"Önce plan modu ile hangi dosyalardan başlanacağını belirleyelim.
 Sonra birer birer ilerleriz."
```

---

## Hata 3: Bağlamı Tekrar Tekrar Açıklamak

Her mesajda projeyi tekrar anlatmak yerine CLAUDE.md kullan.

→ [CLAUDE.md Proje Özeli](../02-claude-md/02-proje-ozeli.tr.md)

---

## Hata 4: Claude'a Çok Geniş İzin Vermek

Her `Bash` komutuna izin verme. İzin listesini minimum tut.

→ [settings.json İzin Yönetimi](../03-hooks-otomasyon/01-settings-json.tr.md)

---

## Hata 5: Sonucu Doğrulamamak

Claude bir şeyi "yaptım" dedi diye test etmeden geçme. Her önemli değişikliği manuel doğrula veya hook ile otomatik test çalıştır.

---

## Hata 6: Uzun Prompt Zincirleri

10 mesajlık konuşmalar yerine bir mesajda netleştir:

```
"Şunu biliyorum: [bağlam]
 Şunu yapmak istiyorum: [hedef]
 Kısıt: [kısıtlar]
 Beklenen çıktı: [format]"
```

---

## → Sonraki Adım

Yaygın hatalardan kaçınmayı öğrendiysen ileri düzey tekniklere geç:

**[05 › İleri Düzey](./04-ileri-duzey.tr.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Hâlâ beklediğim sonucu alamıyorum | [İleri Düzey Teknikler](./04-ileri-duzey.tr.md) |
| CLAUDE.md'ye ne ekleyeceğimi bilemedim | [CLAUDE.md Proje Özeli](../02-claude-md/02-proje-ozeli.tr.md) |
| Bağlam yönetimi konusunda sorunum var | [Bağlam Yönetimi](./02-baglam-yonetimi.tr.md) |
