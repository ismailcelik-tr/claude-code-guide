# 01 › Geliştirme Süreci › Code Review

PR ve kod inceleme sürecinde Claude Code ile verimlilik.

---

## Diff İnceleme

```
/review
```

ya da:

```
"git diff main...HEAD çıktısını incele.
 Güvenlik açığı, performans sorunu ve stil ihlali varsa listele."
```

---

## PR Açıklaması Üretme

```
"Bu branch'teki değişiklikleri özetle.
 GitHub PR açıklaması formatında yaz: Summary, Test Plan, Breaking Changes."
```

---

## Inline Yorum Üretme

```
/review --comment
```

Bu komut PR'daki değişiklikleri okur ve GitHub'a inline yorum olarak gönderir.

---

## Başka Birinin Kodunu İnceleme

```
"Bu PR'ı incele: [dosya içeriği veya diff]
 Sadece gerçek hataları veya önemli sorunları listele.
 Stil yorumu yapma."
```

---

## → Sonraki Adım

Review tamamsa deploy aşamasına geç:

**[01 › Deployment](./05-deployment.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Review çok yüzeysel kaldı | [İleri Düzey Prompt](../05-prompt-stratejileri/04-ileri-duzey.md) |
| Yanlış dosyaları inceledi | [Bağlam Yönetimi](../05-prompt-stratejileri/02-baglam-yonetimi.md) |
| Test eksikliği tespit edildi | [Test & Debug](./03-test-ve-debug.md) |
| Deploy'a geçmek istiyorum | [Deployment](./05-deployment.md) |
