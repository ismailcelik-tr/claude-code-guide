# Şablon: Monorepo CLAUDE.md

Birden fazla paket veya uygulama barındıran repolar için.

---

## Kök CLAUDE.md

```markdown
# [Monorepo Adı]

## Yapı
Bu repo şu paketleri barındırır:
- packages/ui — paylaşılan React bileşen kütüphanesi
- packages/utils — paylaşılan yardımcı fonksiyonlar
- apps/web — kullanıcı uygulaması (Next.js)
- apps/admin — admin paneli (Next.js)
- apps/api — REST API (Node.js)

## Paket Yöneticisi
pnpm workspace kullanılıyor.

## Komutlar
- `pnpm dev` — tüm uygulamaları başlatır
- `pnpm dev --filter=web` — sadece web'i başlatır
- `pnpm test` — tüm testler
- `pnpm build` — tüm build'ler

## Bağımlılık Kuralları
- apps/ paketleri packages/'a bağımlı olabilir
- packages/ paketleri birbirine bağımlı OLMAZ
- Dış paket eklemek için root'tan: `pnpm add <paket> --filter=<app>`

## Genel Kurallar
- TypeScript strict modu açık
- Her pakette kendi test konfigürasyonu var
- Tip değişiklikleri packages/utils'i etkiliyorsa tüm app'leri kontrol et
```

---

## Alt Paket CLAUDE.md (apps/api)

```markdown
# API Uygulaması

@../../CLAUDE.md

## Bu Pakete Özgü
- Port: 3001
- Veritabanı: PostgreSQL, bağlantı DATABASE_URL env'inden
- Migration: `pnpm db:migrate` ile çalıştır

## Önemli Dizinler
- src/routes/ — endpoint tanımları
- src/services/ — iş mantığı
- prisma/ — Prisma schema ve migration'lar
```

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| @import çalışmıyor | [İleri Düzey — Import](../03-ileri-duzey.md) |
| Hangi pakette çalıştığımı Claude anlayamadı | Alt paket CLAUDE.md ekle |
| Full-stack ama monorepo değil | [Full-Stack Şablonu](./fullstack.md) |
