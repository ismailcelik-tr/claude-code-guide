# Claude Code Rehberi

> **Hedef kitle:** Her seviyeden software developer  
> **Amaç:** Uygulama geliştirme sürecinin her aşamasında Claude Code'u en efektif şekilde kullanmak

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

    SDLC --> P1["🟢 Planlama"]
    P1 --> P2["🟢 Geliştirme"]
    P2 --> P3["🟡 Test & Debug"]
    P3 --> P4["🟡 Code Review"]
    P4 --> P5["🔴 Deployment"]

    P3 -- "❌ hata var" --> P2
    P4 -- "❌ test eksik" --> P3
    P5 -- "❌ production patladı" --> P3

    click B00 href "./00-baslangic/README.md"
    click SDLC href "./01-gelistirme-sureci/README.md"
    click P1 href "./01-gelistirme-sureci/01-planlama.md"
    click P2 href "./01-gelistirme-sureci/02-gelistirme.md"
    click P3 href "./01-gelistirme-sureci/03-test-ve-debug.md"
    click P4 href "./01-gelistirme-sureci/04-code-review.md"
    click P5 href "./01-gelistirme-sureci/05-deployment.md"
    click CMD href "./02-claude-md/README.md"
    click HOOK href "./03-hooks-otomasyon/README.md"
    click AJAN href "./04-ajanlar/README.md"
    click PROMPT href "./05-prompt-stratejileri/README.md"

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
```

> Renk skalası: 🟢 Kolay başlangıç — 🟡 Orta — 🟠 İleri — 🔴 Dikkat gerektiren  
> Kırmızı oklar (`❌`) hata durumunda geri dönüş yolunu gösterir.

---

## Bölümler

| # | Bölüm | Ne öğrenirsin |
|---|---|---|
| 00 | [Başlangıç](./00-baslangic/README.md) | Claude Code nedir, kurulum, bu repoyu nasıl takip etmelisin |
| 01 | [Geliştirme Süreci](./01-gelistirme-sureci/README.md) | Planlama → Geliştirme → Test → Review → Deployment |
| 02 | [CLAUDE.md](./02-claude-md/README.md) | Proje bağlamı kurma, şablonlar, import ve memory |
| 03 | [Hooks & Otomasyon](./03-hooks-otomasyon/README.md) | settings.json, hook tipleri, hazır tarifler |
| 04 | [Ajanlar](./04-ajanlar/README.md) | Agent tool, subagent tipleri, paralel çalıştırma |
| 05 | [Prompt Stratejileri](./05-prompt-stratejileri/README.md) | Plan modu, bağlam yönetimi, yaygın hatalar, ileri düzey |

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

Bu repo topluluk katkısına açıktır. Her sayfanın altında eksik veya hatalı bir bilgi görürsen PR aç.
