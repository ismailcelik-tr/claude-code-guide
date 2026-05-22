# Şablon: Full-Stack CLAUDE.md

Frontend + backend barındıran projeler için.

---

```markdown
# [Proje Adı]

## Genel Bakış
[Ne yapar, kimler kullanır — 2-3 cümle]

## Teknoloji Yığını
### Frontend
- Framework: [React / Next.js / Vue]
- Dil: TypeScript
- Stil: [Tailwind / styled-components]
- State: [Zustand / Redux / Context]

### Backend
- Runtime: [Node.js / Python / Go]
- Framework: [Express / FastAPI / Gin]
- Veritabanı: [PostgreSQL / MongoDB]
- Auth: [JWT / OAuth2]

## Dizin Yapısı
```
src/
├── app/          # Next.js app router veya sayfa bileşenleri
├── components/   # paylaşılan UI bileşenleri
├── api/          # API istemci katmanı
├── hooks/        # custom React hooks
└── types/        # paylaşılan TypeScript tipleri

server/
├── routes/       # API route tanımları
├── controllers/  # iş mantığı
├── models/       # veritabanı modelleri
└── middleware/   # Express middleware
```

## Komutlar
- `npm run dev` — frontend + backend birlikte başlatır
- `npm run dev:server` — sadece backend
- `npm test` — tüm testler
- `npm run db:migrate` — migration çalıştır

## Mimari Kararlar
- API iletişimi sadece src/api/ üzerinden
- Veritabanına doğrudan erişim yok — her şey controller üzerinden
- Paylaşılan tipler src/types/ ve server/types/ arasında senkronize tutulur

## Kurallar
- `any` tipi kullanma
- API endpoint'leri versiyonlanır: /api/v1/
- Her yeni endpoint için integration testi zorunlu
- console.log commit'e girmesin

## Test Stratejisi
- Unit: Vitest (src/)
- Integration: Jest + Supertest (server/)
- E2E: Playwright (tests/e2e/)
```

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Monorepo için yetersiz kaldı | [Monorepo Şablonu](./monorepo.tr.md) |
| Daha basit bir şablon istiyorum | [Minimal Şablon](./minimal.tr.md) |
