# 02 › CLAUDE.md › Temel Yapı

## CLAUDE.md Nedir?

Projenin kök dizinine koyduğun bir Markdown dosyasıdır. Claude Code her konuşma başında bu dosyayı okur.

---

## Dosya Konumu {#dosya-konumu}

```
proje-koku/
├── CLAUDE.md        ← buraya
├── src/
└── package.json
```

> [!CAUTION]
> CLAUDE.md'yi `src/` veya başka bir alt dizine koyarsan Claude onu **otomatik okumaz**.
> Her zaman projenin **kök dizinine** koy.

Alt dizinlere de ekleyebilirsin — ancak bu dosyalar yalnızca o dizinde çalışırken okunur.

---

## Temel Yapı

```markdown
# Proje Adı

## Genel Bakış
Projenin ne yaptığını 2-3 cümlede açıkla.

## Teknoloji Yığını
- Frontend: React 18, TypeScript
- Backend: Node.js, Express
- Veritabanı: PostgreSQL

## Dizin Yapısı
- src/components/ — UI bileşenleri
- src/api/ — API katmanı
- src/utils/ — yardımcı fonksiyonlar

## Sık Kullanılan Komutlar
- npm run dev — geliştirme sunucusu
- npm test — testleri çalıştır
- npm run build — production build

## Kurallar
- Her fonksiyon için unit test yaz
- Console.log bırakma
- Türkçe commit mesajı kullan
```

---

## /init ile Otomatik Oluşturma

Mevcut bir projede:

```bash
claude
/init
```

Claude kod tabanını tarar ve taslak bir CLAUDE.md oluşturur. Ardından gözden geçirip düzenle.

---

## → Sonraki Adım

Temel yapıyı kurduysun, projeye özel bağlamı ekle:

**[02 › Proje Özeli](./02-proje-ozeli.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| /init çalışmadı | [00 Başlangıç — Kurulum](../00-baslangic/README.md) |
| Temel yapıyı kurdum, daha fazlasını istiyorum | [Proje Özeli](./02-proje-ozeli.md) |
| Claude hâlâ projeyi anlamıyor | [Proje Özeli — Bağlam Derinleştirme](./02-proje-ozeli.md) |
