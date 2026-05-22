# 03 › Hooks & Otomasyon › Hook Tipleri

## Mevcut Hook Tipleri

| Tip | Ne Zaman Tetiklenir |
|---|---|
| `PreToolUse` | Claude bir araç çağırmadan **önce** |
| `PostToolUse` | Claude bir araç çağırdıktan **sonra** |
| `Notification` | Claude bir bildirim gösterdiğinde |
| `Stop` | Claude görevi tamamladığında |

---

## PreToolUse

Tehlikeli komutları durdurmak veya çalıştırmadan önce kontrol etmek için:

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [
          {
            "type": "command",
            "command": "echo 'Bash komutu çalıştırılıyor' >> ~/.claude/audit.log"
          }
        ]
      }
    ]
  }
}
```

Hook `exit 2` ile çıkarsa Claude o araç çağrısını iptal eder.

---

## PostToolUse

Bir dosya kaydedildikten sonra lint çalıştır:

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit",
        "hooks": [
          {
            "type": "command",
            "command": "npm run lint --silent 2>&1 | head -20"
          }
        ]
      }
    ]
  }
}
```

---

## Stop

Claude işi bitirince çalışır:

```json
{
  "hooks": {
    "Stop": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "osascript -e 'display notification \"Claude tamamladı\" with title \"Claude Code\"'"
          }
        ]
      }
    ]
  }
}
```

---

## → Sonraki Adım

Hook tiplerini öğrendin, hazır tariflerle uygula:

**[03 › Tarifler](./03-tarifler.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Hook tanımı nereye yazılır | [settings.json](./01-settings-json.md) |
| Hazır tarifler istiyorum | [Tarifler](./03-tarifler.md) |
| Hook çalışıyor ama beklenmedik davranıyor | exit kodunu ve command çıktısını kontrol et |
