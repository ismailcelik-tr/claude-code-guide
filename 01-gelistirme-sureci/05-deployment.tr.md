# 01 › Geliştirme Süreci › Deployment

CI/CD entegrasyonu ve deployment sürecinde Claude Code kullanımı.

---

## CI/CD Hatası Analizi

Başarısız pipeline logunu Claude'a ver:

```
"GitHub Actions logunu yapıştırıyorum.
 Hangi adımda neden başarısız oldu, nasıl düzeltilir?"
[log içeriği]
```

---

## Ortam Değişkeni ve Config Yönetimi

```
"Bu .env.example dosyasını oku.
 Production ortam için eksik olan değişkenleri listele."
```

> [!CAUTION]
> Gerçek secret değerlerini (API key, şifre) Claude'a yapıştırma. Sadece değişken isimlerini paylaş.

---

## Docker / Container

```
"Bu Dockerfile'ı incele.
 Image boyutunu küçültmek ve güvenlik açıklarını kapatmak için öneride bulun."
```

---

## Kontrol Listesi {#kontrol-listesi}

Deploy öncesi Claude ile gözden geçir:

```
"Deploy öncesi kontrol listesi oluştur.
 Proje: [proje türü], hedef ortam: [prod/staging], platform: [AWS/Vercel/…]"
```

Claude; migration, env var, bağımlılık, health check gibi maddeleri listeler.

---

## → Sonraki Adım

Süreci otomatikleştirmek istiyorsan:

**[03 › Hooks & Otomasyon](../03-hooks-otomasyon/README.tr.md)**

Ya da Claude Code'u daha verimli kullanmak için:

**[05 › Prompt Stratejileri](../05-prompt-stratejileri/README.tr.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| CI/CD logunu anlayamıyorum | Bu sayfanın "CI/CD Hatası Analizi" bölümü |
| Deploy sonrası production patlıyor | [Test & Debug](./03-test-ve-debug.tr.md) |
| Ortam değişkenleri eksik | Bu sayfanın "Ortam Değişkeni" bölümü |
| Başa dönmem gerekiyor | [Geliştirme Süreci Ana Sayfa](./README.tr.md) |
