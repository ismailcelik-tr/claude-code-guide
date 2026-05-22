# 04 › Ajanlar › Subagent Tipleri

## Mevcut Subagent Tipleri

| Tip | Ne İçin |
|---|---|
| `Explore` | Kod tabanı araştırma, dosya bulma, sembol arama |
| `Plan` | Uygulama planı tasarlama, mimari önerisi |
| `claude` | Genel amaçlı, tüm araçlara erişim |
| `general-purpose` | Geniş kapsamlı araştırma ve çok adımlı görevler |
| `claude-code-guide` | Claude Code CLI ve API hakkında sorular |

---

## Explore — Ne Zaman?

Sadece araştırma yapacaksan ve dosya **değiştirmeyeceksen**:

```
"Explore subagent'i kullanarak:
 - Tüm React component dosyalarını listele
 - Her birinin hangi hook'ları kullandığını bul"
```

Explore; Edit ve Write araçlarına erişimi olmadığı için yanlışlıkla değişiklik yapamaz.

---

## Plan — Ne Zaman?

Uygulamaya başlamadan önce mimari veya yaklaşım onayı almak için:

```
"Plan subagent'i kullanarak şu özelliğin implementasyon planını çıkar:
 [özellik açıklaması]
 Mevcut dosya yapısını göz önünde bulundur."
```

---

## claude (Genel) — Ne Zaman?

Araştırma + uygulama birlikte yapılacaksa ya da özel araç erişimi gerekiyorsa.

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Explore ajan dosya değiştirdi | Olmaz — Explore'un Edit/Write erişimi yok |
| Plan ajanı çok detaylı/genel kaldı | Prompt'a kısıtları ve bağlamı ekle |
| Hangi tipi seçeceğimi bilemedim | Kural: sadece okuyorsa Explore, planlıyorsa Plan, ikisi birlikte ise claude |
