# 03 › Hooks & Otomasyon › settings.json

## Konum ve Format {#konum-ve-format}

İki konum vardır:

| Dosya | Kapsam |
|---|---|
| `~/.claude/settings.json` | Tüm projeler (global) |
| `.claude/settings.json` | Sadece bu proje (proje düzeyi) |

> [!CAUTION]
> `.claude/settings.json` dosyasının `.claude/` dizini içinde olduğundan emin ol.
> Proje kökünde `settings.json` olarak bırakırsan Claude onu okumaz.

---

## Temel Yapı

```json
{
  "permissions": {
    "allow": [],
    "deny": []
  },
  "hooks": {
    "PreToolUse": [],
    "PostToolUse": [],
    "Notification": [],
    "Stop": []
  }
}
```

---

## İzin Tanımları

```json
{
  "permissions": {
    "allow": [
      "Bash(npm run *)",
      "Bash(git status)",
      "Bash(git diff *)",
      "Edit(src/**)",
      "Read(**)"
    ],
    "deny": [
      "Bash(rm -rf *)",
      "Bash(git push --force)"
    ]
  }
}
```

Glob desteklenir: `*` tek segment, `**` çok segment.

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| settings.json nerede diye soruyorum | Bu sayfanın "Konum" bölümü |
| Hook tipleri neler | [Hook Tipleri](./02-hook-tipleri.md) |
| İzin verdiğim komut hâlâ sorgulanıyor | Glob pattern'i kontrol et |
