# Senaryo 01 › Sıfırdan SaaS

**Durum:** Yeni bir SaaS projesi başlatıyorsun. Boş dizin, hiç CLAUDE.md yok, nereden başlayacağını bilmiyorsun.

**Zorluk:** 🟢 Başlangıç  
**Süre:** ~30 dakika ilk kurulum

---

## Adım 1 — Proje Dizinini Oluştur ve Claude'u Başlat

```bash
mkdir my-saas && cd my-saas
git init
claude
```

---

## Adım 2 — CLAUDE.md'yi Manuel Yaz

Henüz kod tabanı olmadığı için `/init` çalışmaz. İlk CLAUDE.md'yi elle yaz:

```
"Bir SaaS projesi kuruyorum. Teknoloji: Next.js 14, TypeScript,
 PostgreSQL, Prisma. Auth için NextAuth kullanacağız.
 Bu projeye uygun bir CLAUDE.md oluştur."
```

Claude bir taslak üretir. Gözden geçir, projeye özgü kuralları ekle, kaydet.

→ Şablon için: [Full-Stack CLAUDE.md](../02-claude-md/ornekler/fullstack.md)

---

## Adım 3 — Mimariyi Planla

```
"Şu stack ile bir SaaS projesi kuruyoruz:
 Next.js 14 (App Router), TypeScript, PostgreSQL, Prisma, NextAuth.

 Başlamadan önce:
 1. Dizin yapısını öner
 2. İlk oluşturulacak dosyaları listele
 3. Potansiyel sorunları belirt

 Planını göster, onaylayayım."
```

Plan moduna girer, onayından sonra ilerler.

---

## Adım 4 — İskelet Kodu Oluştur

Planı onayladıktan sonra aşama aşama ilerle. Hepsini bir anda isteme:

```
"Önce sadece temel dizin yapısını ve boş dosyaları oluştur.
 İçerik doldurmaya henüz başlama."
```

Ardından:

```
"Şimdi Prisma schema'sını yaz. Kullanıcı ve abonelik modeli olsun."
```

---

## Adım 5 — Hook'ları Kur

Geliştirmeye başlamadan önce otomasyonu yerleştir:

```
"Bu proje için .claude/settings.json oluştur.
 npm run lint ve npm run typecheck'i her Edit'ten sonra çalıştırsın."
```

→ Detay: [Hooks & Otomasyon](../03-hooks-otomasyon/README.md)

---

## Adım 6 — İlk Özelliği Geliştir

Artık altyapı hazır. Her özellik için döngü:

```
Plan → Geliştir → Test → Review → commit
```

```
"Kullanıcı kaydı ve girişini implement et.
 NextAuth + Prisma kullanarak.
 Her adımı tamamladıktan sonra dur, onaylayayım."
```

---

## Bu Senaryoda Sık Yapılan Hatalar

| Hata | Neden Olur | Çözüm |
|---|---|---|
| CLAUDE.md yazmadan koda dalmak | Zaman kazanmak | Claude projeyi bilmeden çalışır — her konuşmada bağlamı yeniden açıklamak zorunda kalırsın |
| Tüm uygulamayı tek promptla istemek | Hırs | Claude ya çok yüzeysel kalır ya da fazla varsayım yapar |
| Hook kurmadan geliştirmeye başlamak | Acele | Lint hataları birikir, sonradan temizlemek zor olur |

---

## → Sonraki Adım

Bu senaryo tamamlandıysa, mevcut kodu modernize etmeyi öğren:

**[Senaryo 02 › Legacy Modernizasyon](./02-legacy-modernizasyon.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| /plan komutu nasıl çalışır | [Plan Modu](../05-prompt-stratejileri/01-plan-modu.md) |
| CLAUDE.md'yi nasıl yazacağımı bilemedim | [CLAUDE.md Temel Yapı](../02-claude-md/01-temel-yapi.md) |
| Hook kurulumu başarısız | [settings.json](../03-hooks-otomasyon/01-settings-json.md) |
