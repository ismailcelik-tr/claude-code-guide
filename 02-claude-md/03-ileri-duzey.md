# 02 › CLAUDE.md › İleri Düzey

Import, memory sistemi ve izin yönetimi.

---

## @import ile Parçalama

CLAUDE.md çok büyüdüğünde parçalara böl:

```markdown
# CLAUDE.md

@./docs/architecture.md
@./docs/conventions.md
@./docs/testing.md
```

Her `@` satırı ilgili dosyanın içeriğini sanki doğrudan yazılmış gibi dahil eder.

---

## Memory Sistemi

Claude Code'un kalıcı belleği `~/.claude/projects/` altında proje başına saklanır.

**Manuel kaydetme:**
```
"Bunu hatırla: Bu projede migration'lar schema/ altında yaşıyor."
```

**Ne zaman kullanılır:**
- Her konuşmada tekrarladığın bilgiler
- CLAUDE.md'ye koymak istemediğin kişisel tercihler

---

## İzin Yönetimi

`~/.claude/settings.json` veya `.claude/settings.json`:

```json
{
  "permissions": {
    "allow": [
      "Bash(npm run *)",
      "Bash(git *)",
      "Edit(src/**)"
    ],
    "deny": [
      "Bash(rm -rf *)"
    ]
  }
}
```

→ Detaylar için: [settings.json](../03-hooks-otomasyon/01-settings-json.md)

---

## → Sonraki Adım

CLAUDE.md'yi kurduysun, tekrarlayan işleri otomatikleştir:

**[03 › Hooks & Otomasyon](../03-hooks-otomasyon/README.md)**

---

## ↩ Bir Şeyler Ters Gittiyse

| Durum | Geri Dön |
|---|---|
| @import çalışmıyor | [Temel Yapı — Dosya Konumu](./01-temel-yapi.md#dosya-konumu) |
| İzin verdiğim komut hâlâ soruluyor | [settings.json](../03-hooks-otomasyon/01-settings-json.md) |
| Memory'e kaydettiğim şey unutuldu | [Bağlam Yönetimi](../05-prompt-stratejileri/02-baglam-yonetimi.md) |
