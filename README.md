<div align="center">

<img src="./assets/claude-icon.svg" width="80" alt="Claude Code Rehberi"/>

# Claude Code Rehberi

[![License: MIT](https://img.shields.io/badge/Lisans-MIT-green?style=for-the-badge)](./LICENSE)
[![Language](https://img.shields.io/badge/Dil-Türkçe-blue?style=for-the-badge)](./README.md)
[![Built for Claude Code](https://img.shields.io/badge/Claude%20Code%20için-DA7756?style=for-the-badge&logo=data:image/svg%2bxml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxMDAgMTAwIj48ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSg1MCw1MCkiIGZpbGw9IiNmZmYiPjxyZWN0IHg9Ii00IiB5PSItMzAiIHdpZHRoPSI4IiBoZWlnaHQ9IjI4IiByeD0iNCIvPjxyZWN0IHg9Ii00IiB5PSItMzAiIHdpZHRoPSI4IiBoZWlnaHQ9IjI4IiByeD0iNCIgdHJhbnNmb3JtPSJyb3RhdGUoNDUpIi8+PHJlY3QgeD0iLTQiIHk9Ii0zMCIgd2lkdGg9IjgiIGhlaWdodD0iMjgiIHJ4PSI0IiB0cmFuc2Zvcm09InJvdGF0ZSg5MCkiLz48cmVjdCB4PSItNCIgeT0iLTMwIiB3aWR0aD0iOCIgaGVpZ2h0PSIyOCIgcng9IjQiIHRyYW5zZm9ybT0icm90YXRlKDEzNSkiLz48cmVjdCB4PSItNCIgeT0iLTMwIiB3aWR0aD0iOCIgaGVpZ2h0PSIyOCIgcng9IjQiIHRyYW5zZm9ybT0icm90YXRlKDE4MCkiLz48cmVjdCB4PSItNCIgeT0iLTMwIiB3aWR0aD0iOCIgaGVpZ2h0PSIyOCIgcng9IjQiIHRyYW5zZm9ybT0icm90YXRlKDIyNSkiLz48cmVjdCB4PSItNCIgeT0iLTMwIiB3aWR0aD0iOCIgaGVpZ2h0PSIyOCIgcng9IjQiIHRyYW5zZm9ybT0icm90YXRlKDI3MCkiLz48cmVjdCB4PSItNCIgeT0iLTMwIiB3aWR0aD0iOCIgaGVpZ2h0PSIyOCIgcng9IjQiIHRyYW5zZm9ybT0icm90YXRlKDMxNSkiLz48L2c+PC9zdmc+&logoColor=white)](https://claude.ai/code)
[![Scenarios](https://img.shields.io/badge/Senaryolar-8-8b5cf6?style=for-the-badge)](./06-senaryolar/README.md)
[![Contributing](https://img.shields.io/badge/Katkı-Açık-orange?style=for-the-badge)](./CONTRIBUTING.md)

**Her seviyeden software developer için uygulama geliştirme sürecinin her aşamasında Claude Code rehberi**

</div>

---

Aşağıdaki diyagramda **şu an bulunduğun noktayı** seç ve ilgili bölüme geç. Yanlış bir adım attıysan her sayfanın altındaki **↩ Bir Şeyler Ters Gittiyse** tablosu seni doğru noktaya geri getirir.

---

## Navigasyon

```mermaid
flowchart TD
    START([🚀 Başlangıç]) --> KARAR{Neredesin?}

    KARAR -->|Sıfırdan başlıyorum| B00["🟢 00 · Başlangıç\nKurulum & ilk adımlar"]
    KARAR -->|Uygulama geliştiriyorum| SDLC["🔵 01 · Geliştirme Süreci"]
    KARAR -->|CLAUDE.md yok / eksik| CMD["🟡 02 · CLAUDE.md"]
    KARAR -->|Otomasyon lazım| HOOK["🟡 03 · Hooks & Otomasyon"]
    KARAR -->|Agent kullanacağım| AJAN["🟠 04 · Ajanlar"]
    KARAR -->|Prompt verimsiz| PROMPT["🔴 05 · Prompt Stratejileri"]
    KARAR -->|Gerçek örnekler istiyorum| SCN["📖 06 · Senaryolar"]

    SDLC --> P1["🟢 Planlama"]
    P1 --> P2["🟢 Geliştirme"]
    P2 --> P3["🟡 Test & Debug"]
    P3 --> P4["🟡 Code Review"]
    P4 --> P5["🔴 Deployment"]

    P3 -- "❌ hata var" --> P2
    P4 -- "❌ test eksik" --> P3
    P5 -- "❌ production patladı" --> P3

    click B00 href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/00-baslangic/README.md"
    click SDLC href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/01-gelistirme-sureci/README.md"
    click P1 href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/01-gelistirme-sureci/01-planlama.md"
    click P2 href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/01-gelistirme-sureci/02-gelistirme.md"
    click P3 href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/01-gelistirme-sureci/03-test-ve-debug.md"
    click P4 href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/01-gelistirme-sureci/04-code-review.md"
    click P5 href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/01-gelistirme-sureci/05-deployment.md"
    click CMD href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/02-claude-md/README.md"
    click HOOK href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/03-hooks-otomasyon/README.md"
    click AJAN href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/04-ajanlar/README.md"
    click PROMPT href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/05-prompt-stratejileri/README.md"
    click SCN href "https://github.com/ismailcelik-tr/claude-code-guide/blob/main/06-senaryolar/README.md"

    style START fill:#1a1a2e,color:#fff,stroke:#7c3aed
    style KARAR fill:#1e3a5f,color:#fff,stroke:#3b82f6
    style B00 fill:#14532d,color:#fff,stroke:#22c55e
    style SDLC fill:#1e3a5f,color:#fff,stroke:#3b82f6
    style P1 fill:#14532d,color:#fff,stroke:#22c55e
    style P2 fill:#14532d,color:#fff,stroke:#22c55e
    style P3 fill:#713f12,color:#fff,stroke:#eab308
    style P4 fill:#713f12,color:#fff,stroke:#eab308
    style P5 fill:#7f1d1d,color:#fff,stroke:#ef4444
    style CMD fill:#713f12,color:#fff,stroke:#eab308
    style HOOK fill:#713f12,color:#fff,stroke:#eab308
    style AJAN fill:#7c2d12,color:#fff,stroke:#f97316
    style PROMPT fill:#7f1d1d,color:#fff,stroke:#ef4444
    style SCN fill:#1e3a5f,color:#fff,stroke:#818cf8
```

> Renk skalası: 🟢 Kolay başlangıç — 🟡 Orta — 🟠 İleri — 🔴 Dikkat gerektiren  
> Kırmızı oklar (`❌`) hata durumunda geri dönüş yolunu gösterir.

---

## Bölümler

| # | Bölüm | Ne öğrenirsin |
|---|---|---|
| ⚡ | [Hızlı Başvuru Kartı](./cheatsheet.md) | Tüm komutlar, kısayollar, şablonlar ve hook tarifleri tek sayfada |
| 00 | [Başlangıç](./00-baslangic/README.md) | Claude Code nedir, kurulum, bu repoyu nasıl takip etmelisin |
| 01 | [Geliştirme Süreci](./01-gelistirme-sureci/README.md) | Planlama → Geliştirme → Test → Review → Deployment |
| 02 | [CLAUDE.md](./02-claude-md/README.md) | Proje bağlamı kurma, şablonlar, import ve memory |
| 03 | [Hooks & Otomasyon](./03-hooks-otomasyon/README.md) | settings.json, hook tipleri, hazır tarifler |
| 04 | [Ajanlar](./04-ajanlar/README.md) | Agent tool, subagent tipleri, paralel çalıştırma |
| 05 | [Prompt Stratejileri](./05-prompt-stratejileri/README.md) | Plan modu, bağlam yönetimi, yaygın hatalar, ileri düzey |
| 06 | [Gerçek Senaryolar](./06-senaryolar/README.md) | Sıfırdan SaaS, legacy modernizasyon, production krizi, yeni özellik ekleme |

---

## Hızlı Geri Dönüş Haritası

| Durum | Geri Dön |
|---|---|
| Claude projeyi anlamamış gibi davranıyor | [CLAUDE.md Temel Yapı](./02-claude-md/01-temel-yapi.md) |
| Hook hiç tetiklenmiyor | [settings.json Konumu](./03-hooks-otomasyon/01-settings-json.md#konum-ve-format) |
| Ajan beklenen sonucu döndürmüyor | [Agent Tool — Temel Kullanım](./04-ajanlar/01-agent-tool.md) |
| Claude çok fazla / az kod yazıyor | [Yaygın Hatalar](./05-prompt-stratejileri/03-yaygin-hatalar.md) |
| Deploy adımında CI/CD bozuldu | [Deployment Kontrol Listesi](./01-gelistirme-sureci/05-deployment.md#kontrol-listesi) |
| Context doldu, konuşma kayboldu | [Bağlam Yönetimi](./05-prompt-stratejileri/02-baglam-yonetimi.md) |
| Test geçiyor ama production patlıyor | [Test & Debug](./01-gelistirme-sureci/03-test-ve-debug.md) |

---

## Katkı

Bu repo topluluk katkısına açıktır.

- Hata veya eksik bildi → [Issue aç](https://github.com/ismailcelik-tr/claude-code-guide/issues/new)
- İçerik katkısı → [CONTRIBUTING.md](./CONTRIBUTING.md)
- Güvenlik bildirimi → [SECURITY.md](./SECURITY.md)
- Lisans → [MIT](./LICENSE)
