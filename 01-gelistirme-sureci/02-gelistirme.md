# 01 › Geliştirme Süreci › Geliştirme

Aktif kod yazarken Claude Code'u nasıl kullanırsın.

---

## Dosya Okuma ve Düzenleme

Claude, izin verdiğinde dosyaları doğrudan okur ve düzenler. Hangi dosyayı neden değiştireceğini sana gösterir, onay bekler.

**İyi prompt örneği:**
```
"src/auth/login.ts dosyasındaki validateUser fonksiyonuna
 rate limiting ekle. Mevcut testi bozmadan yap."
```

**Kaçın:**
```
"Auth sistemini iyileştir."  ← çok belirsiz
```

---

## Refactoring

```
"Bu dosyayı oku ve tekrar eden kodu extract et.
 Değiştireceğin her şeyi önce listele, sonra uygula."
```

Büyük refactorlar için plan modunu kullan → [Planlama](./01-planlama.md)

---

## Yeni Özellik Ekleme

1. Önce ilgili mevcut kodu Claude'a okut
2. Neyin nereye ekleneceğini Claude'a söyle
3. Oluşturulan kodu gözden geçir, ardından onayla

```
"Şu an şu dosyalar mevcut: [dosya listesi].
 Bunlara dokunmadan yeni bir payment modülü ekle."
```

---

## Araç İzinleri

Claude Code bazı komutlar için izin ister. Sık kullandığın komutlar için izin verirken dikkatli ol:

- `Bash` — terminal komutları
- `Edit` / `Write` — dosya değişiklikleri
- `WebFetch` — internet erişimi

→ İzin yönetimi için: [settings.json](../03-hooks-otomasyon/01-settings-json.md)

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Claude çok fazla dosyayı değiştirdi | [Yaygın Hatalar](../05-prompt-stratejileri/03-yaygin-hatalar.md) |
| Claude yanlış dosyayı düzenledi | [CLAUDE.md Proje Özeli](../02-claude-md/02-proje-ozeli.md) |
| Yazdığım kod test edilmeden geçti | [Test & Debug](./03-test-ve-debug.md) |
