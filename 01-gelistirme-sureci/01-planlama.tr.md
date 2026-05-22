# 01 › Geliştirme Süreci › Planlama

Bir projeye başlamadan önce Claude Code ile nasıl plan kurarsın.

---

## Plan Modu

Büyük veya belirsiz bir görev başlatmadan önce plan moduna gir:

```
/plan
```

ya da doğrudan Claude Code'a söyle:

> "Bu göreve başlamadan önce planını görmek istiyorum."

Claude; dosya yapısını inceler, yaklaşım önerir ve onayını bekler — uygulamaya başlamaz.

**Ne zaman kullan:**
- Birden fazla dosyayı etkileyecek değişiklikler
- Mimari kararlar gerektiren özellikler
- Gereksinimlerin henüz netleşmediği durumlar

---

## Proje Başında CLAUDE.md Oluştur

Her yeni projede ilk iş:

```bash
claude
# sonra:
/init
```

`/init` mevcut kod tabanını okuyup `CLAUDE.md` taslağı oluşturur. Bunu projenin kök dizininde çalıştır.

→ Detaylar için: [CLAUDE.md Temel Yapı](../02-claude-md/01-temel-yapi.tr.md)

---

## Büyük Görevi Küçük Parçalara Bölme

Claude'a tüm görevi bir anda verme. Bunun yerine:

```
"Kullanıcı kayıt sistemini implement edeceğiz.
 Önce görevleri listele, sonra birer birer ilerleyelim."
```

Her adımı onayladıktan sonra bir sonrakine geç.

---

## Referans Bağlantılar

- [Plan Modu Detayları](../05-prompt-stratejileri/01-plan-modu.tr.md)
- [CLAUDE.md ile Proje Bağlamı Kurma](../02-claude-md/02-proje-ozeli.tr.md)

---

## → Sonraki Adım

Planını onayladıysan koda geçme zamanı:

**[01 › Geliştirme](./02-gelistirme.tr.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Plan modu nasıl çalışır bilmiyorum | [Plan Modu](../05-prompt-stratejileri/01-plan-modu.tr.md) |
| /init çalışmadı veya CLAUDE.md boş çıktı | [CLAUDE.md Temel Yapı](../02-claude-md/01-temel-yapi.tr.md) |
| Görev çok büyük, nereden başlayacağım belli değil | Bu sayfanın "Büyük Görevi Böl" bölümü |
