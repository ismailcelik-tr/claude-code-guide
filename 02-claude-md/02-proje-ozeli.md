# 02 › CLAUDE.md › Proje Özeli

Temel yapının ötesinde, projeye özel bağlam ekleme.

---

## Ne Kadar Detay Yeterli?

**Az:** Claude projeyi yanlış anlar, sık sık düzeltmen gerekir.  
**Fazla:** CLAUDE.md şişer, güncel tutmak zorlaşır.

Altın kural: Claude'un **bir defadan fazla sormak zorunda kaldığı her şeyi** CLAUDE.md'ye ekle.

---

## Proje Özeli Eklemeler

### Yasaklar ve Kısıtlar

```markdown
## Kısıtlar
- lodash kullanma, native JS metotlarını tercih et
- any tipi kullanma
- src/legacy/ dizinine dokunma — migrasyon yapılıyor
```

### Mimari Kararlar

```markdown
## Mimari
- State yönetimi için Zustand kullanıyoruz (Redux yok)
- API çağrıları sadece src/api/ içinden yapılır
- Shared tipler src/types/index.ts'te tanımlanır
```

### Test Stratejisi

```markdown
## Testler
- Unit testler: Vitest
- E2E testler: Playwright, tests/e2e/ dizininde
- Her PR'da en az %80 coverage bekleniyor
```

### Takım Sözleşmeleri

```markdown
## Commit Formatı
feat: yeni özellik
fix: hata düzeltme
refactor: kod iyileştirme
```

---

## Alt Dizin CLAUDE.md

Büyük projelerde her modül kendi CLAUDE.md'sine sahip olabilir:

```
proje/
├── CLAUDE.md              # genel kurallar
├── frontend/
│   └── CLAUDE.md          # frontend'e özel
└── backend/
    └── CLAUDE.md          # backend'e özel
```

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| CLAUDE.md çok büyüdü, yavaşladı | [İleri Düzey — Import](./03-ileri-duzey.md) |
| Monorepo'da hangi dizine koyacağımı bilemedim | [Monorepo Şablonu](./ornekler/monorepo.md) |
| Claude hâlâ kısıtlara uymadı | [Yaygın Hatalar](../05-prompt-stratejileri/03-yaygin-hatalar.md) |
