# 03 › Hooks & Otomasyon › Tarifler

Kopyala-yapıştır kullanıma hazır hook örnekleri.

---

## Tarif 1: Her Düzenlemede Otomatik Lint

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit",
        "hooks": [
          {
            "type": "command",
            "command": "npm run lint --silent 2>&1 | tail -5"
          }
        ]
      }
    ]
  }
}
```

---

## Tarif 2: Tehlikeli Komut Engelleme

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [
          {
            "type": "command",
            "command": "if echo \"$CLAUDE_TOOL_INPUT\" | grep -qE 'rm -rf|drop table|truncate'; then echo 'Tehlikeli komut engellendi!' >&2; exit 2; fi"
          }
        ]
      }
    ]
  }
}
```

---

## Tarif 3: Tamamlanma Bildirimi (macOS)

```json
{
  "hooks": {
    "Stop": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "osascript -e 'display notification \"Görev tamamlandı\" with title \"Claude Code\" sound name \"Glass\"'"
          }
        ]
      }
    ]
  }
}
```

---

## Tarif 4: Git Commit Öncesi Test

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash(git commit*)",
        "hooks": [
          {
            "type": "command",
            "command": "npm test -- --run 2>&1 | tail -10"
          }
        ]
      }
    ]
  }
}
```

---

## → Sonraki Adım

Otomasyonu kurduysan ajan kullanımına geç:

**[04 › Ajanlar](../04-ajanlar/README.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| Tarif çalışmıyor | [settings.json Konumu](./01-settings-json.md#konum-ve-format) |
| Hangi hook tipini kullanacağımı bilemedim | [Hook Tipleri](./02-hook-tipleri.md) |
| exit 2 ne işe yarar | [PreToolUse Açıklaması](./02-hook-tipleri.md) |
