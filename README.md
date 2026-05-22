# Claude Code Rehberi

> **Hedef kitle:** Her seviyeden software developer  
> **Amaç:** Uygulama geliştirme sürecinin her aşamasında Claude Code'u en efektif şekilde kullanmak

---

## Nasıl Kullanılır?

Aşağıdaki ağaçta **şu an bulunduğun noktayı** seç. Her düğüm ilgili rehbere bağlıdır. Yanlış bir adım attıysan her sayfanın altındaki **↩ Bir Şeyler Ters Gittiyse** tablosu seni doğru noktaya geri getirir.

---

## Navigasyon Ağacı

```
┌─────────────────────────────────────────────────────┐
│                    BAŞLANGIÇ                        │
└──────────────────────┬──────────────────────────────┘
                       │
                       ▼
            🔵 Neredesin şu an?
                       │
   ┌───────────────────┼────────────────────────────┐
   │                   │                            │
   ▼                   ▼                            ▼
```

<details>
<summary>🟢 <strong>Claude Code'u hiç kullanmadım, sıfırdan başlıyorum</strong></summary>

👉 [00 › Başlangıç Rehberi](./00-baslangic/README.md)

Bu bölümde:
- Claude Code nedir, ne değildir
- Kurulum ve ilk adımlar
- Bu repoyu nasıl takip etmelisin

> [!TIP]
> Başlangıç bölümünü okuduktan sonra doğrudan **Geliştirme Süreci** ağacına geçebilirsin.

</details>

---

<details>
<summary>🟡 <strong>Bir uygulama geliştiriyorum — Claude Code'u sürece entegre etmek istiyorum</strong></summary>

👉 [01 › Geliştirme Süreci](./01-gelistirme-sureci/README.md)

```
01-gelistirme-sureci/
      │
      ├── 🟢 Henüz planlamadayım
      │        └──▶ [Planlama](./01-gelistirme-sureci/01-planlama.md)
      │
      ├── 🟢 Aktif olarak kod yazıyorum
      │        └──▶ [Geliştirme](./01-gelistirme-sureci/02-gelistirme.md)
      │
      ├── 🟡 Testler yazıyor veya hata ayıklıyorum
      │        └──▶ [Test & Debug](./01-gelistirme-sureci/03-test-ve-debug.md)
      │
      ├── 🟡 PR / kod inceleme sürecindeyim
      │        └──▶ [Code Review](./01-gelistirme-sureci/04-code-review.md)
      │
      └── 🔴 Deploy aşamasındayım veya CI/CD kuruyorum
               └──▶ [Deployment](./01-gelistirme-sureci/05-deployment.md)
```

> [!WARNING]
> Deployment adımına geçmeden önce test aşamasını tamamladığından emin ol.
> Atladıysan → [Test & Debug](./01-gelistirme-sureci/03-test-ve-debug.md)

</details>

---

<details>
<summary>🟡 <strong>Projem var ama CLAUDE.md kurmadım / düzgün yapılandırmadım</strong></summary>

👉 [02 › CLAUDE.md Rehberi](./02-claude-md/README.md)

```
02-claude-md/
      │
      ├── 🟢 CLAUDE.md nedir bilmiyorum
      │        └──▶ [Temel Yapı](./02-claude-md/01-temel-yapi.md)
      │
      ├── 🟢 Temel yapıyı biliyorum, projeye özel ayarlamak istiyorum
      │        └──▶ [Proje Özeli](./02-claude-md/02-proje-ozeli.md)
      │
      ├── 🟡 İleri düzey özellikler (import, memory, izinler)
      │        └──▶ [İleri Düzey](./02-claude-md/03-ileri-duzey.md)
      │
      └── 📄 Hazır şablonlar
               ├──▶ [Minimal](./02-claude-md/ornekler/minimal.md)
               ├──▶ [Full-Stack](./02-claude-md/ornekler/fullstack.md)
               └──▶ [Monorepo](./02-claude-md/ornekler/monorepo.md)
```

> [!CAUTION]
> CLAUDE.md'yi yanlış dizine koyduysan Claude onu görmez.
> → [Temel Yapı — Dosya Konumu](./02-claude-md/01-temel-yapi.md#dosya-konumu)

</details>

---

<details>
<summary>🟡 <strong>CLAUDE.md var ama tekrarlayan işleri otomatikleştirmek istiyorum</strong></summary>

👉 [03 › Hooks & Otomasyon](./03-hooks-otomasyon/README.md)

```
03-hooks-otomasyon/
      │
      ├── 🟢 settings.json yapısını anlamak istiyorum
      │        └──▶ [settings.json](./03-hooks-otomasyon/01-settings-json.md)
      │
      ├── 🟡 Hook tiplerini (PreToolUse, PostToolUse…) öğrenmek istiyorum
      │        └──▶ [Hook Tipleri](./03-hooks-otomasyon/02-hook-tipleri.md)
      │
      └── 🟡 Hazır hook tarifleri istiyorum
               └──▶ [Tarifler](./03-hooks-otomasyon/03-tarifler.md)
```

> [!WARNING]
> Hook çalışmıyorsa önce settings.json konumunu kontrol et.
> → [settings.json — Konum ve Format](./03-hooks-otomasyon/01-settings-json.md#konum-ve-format)

</details>

---

<details>
<summary>🟠 <strong>Agent / subagent kullanacağım veya paralel görevler çalıştırmak istiyorum</strong></summary>

👉 [04 › Ajanlar](./04-ajanlar/README.md)

```
04-ajanlar/
      │
      ├── 🟢 Agent tool nedir, ne zaman kullanılır
      │        └──▶ [Agent Tool](./04-ajanlar/01-agent-tool.md)
      │
      ├── 🟡 Subagent tiplerini (Explore, Plan, code-review…) anlamak istiyorum
      │        └──▶ [Subagent Tipleri](./04-ajanlar/02-subagent-tipleri.md)
      │
      └── 🔴 Paralel ajan çalıştırmak istiyorum
               └──▶ [Paralel Çalıştırma](./04-ajanlar/03-paralel-calistirma.md)
```

> [!CAUTION]
> Ajan sonuç döndürmiyorsa bağımsız görev olup olmadığını kontrol et.
> → [Paralel Çalıştırma — Ne Zaman Paralel?](./04-ajanlar/03-paralel-calistirma.md#ne-zaman-paralel)

</details>

---

<details>
<summary>🔴 <strong>Prompt'larım verimsiz — Claude beklediğim gibi davranmıyor</strong></summary>

👉 [05 › Prompt Stratejileri](./05-prompt-stratejileri/README.md)

```
05-prompt-stratejileri/
      │
      ├── 🟢 Plan modunu anlayıp kullanmak istiyorum
      │        └──▶ [Plan Modu](./05-prompt-stratejileri/01-plan-modu.md)
      │
      ├── 🟡 Bağlam yönetimi — context dolduğunda ne yapmalıyım
      │        └──▶ [Bağlam Yönetimi](./05-prompt-stratejileri/02-baglam-yonetimi.md)
      │
      ├── 🟡 Yaygın hataları ve kaçınma yollarını görmek istiyorum
      │        └──▶ [Yaygın Hatalar](./05-prompt-stratejileri/03-yaygin-hatalar.md)
      │
      └── 🔴 İleri düzey teknikler (memory, /think, sıkıştırma)
               └──▶ [İleri Düzey](./05-prompt-stratejileri/04-ileri-duzey.md)
```

</details>

---

## Hızlı Geri Dönüş Haritası

Herhangi bir aşamada sıkıştıysan bu tablo ile en yakın geri adımı bul:

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
