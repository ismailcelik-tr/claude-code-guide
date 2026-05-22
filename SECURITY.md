# Güvenlik Politikası

---

## Bu Repo Hakkında

Bu repo yalnızca **dokümantasyon** içerir — çalıştırılabilir kod barındırmaz. Klasik bir güvenlik açığı bildirimi senaryosu geçerli değildir.

Ancak içerikteki güvenlik açısından **yanlış veya tehlikeli tavsiyeler** için aşağıdaki süreci izle.

---

## Güvenlik Açısından Hatalı İçerik Bildirme

Rehberde güvenlik riski oluşturabilecek bir tavsiye (örneğin: tehlikeli izin önerisi, secret yönetimi hatası, güvensiz hook örneği) gördüysen:

1. **Kamuya açık issue açma** — önce e-posta ile bildir
2. İletişim: GitHub üzerinden [@ismailcelik-tr](https://github.com/ismailcelik-tr) profiline DM gönder
3. Konu başlığına `[SECURITY]` ekle

---

## Güvenli Kullanım Hatırlatmaları

Bu rehberi uygularken şunlara dikkat et:

- **Secret ve API key'leri Claude'a yapıştırma** — sadece değişken adlarını paylaş
- **`deny` listesini boş bırakma** — en azından `rm -rf` ve `git push --force` engelle
- **Hook komutlarını production'da test et** — beklenmedik yan etkileri önlemek için önce staging'de dene
- **settings.json'ı git'e commit etmeden önce** içinde hassas bilgi olmadığını kontrol et

---

## Teşekkür

Güvenlik bildirimi yapan katkıcılar CONTRIBUTING.md'de belirtilecektir (isterlerse).
