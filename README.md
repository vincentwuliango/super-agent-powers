# Chief Operational System — Paket Antigravity

Restrukturisasi dari `chief-operational-skills` menjadi dua lapisan konfigurasi native Antigravity: **Rules** (selalu aktif) dan **Skills** (on-demand, dipicu sendiri oleh agent).

## Peta Isi

| Folder | Protokol Asli | Kenapa di sini |
|---|---|---|
| `rules/core-identity-anti-sycophancy.md` | A1, A2 | Persona & anti-validasi harus aktif di 100% respons |
| `rules/privacy-anonymity.md` | A4 | Larangan personalisasi harus aktif di 100% respons |
| `rules/response-structure.md` | A7, A10, A11 | Format Date/Role/TL;DR harus konsisten di setiap respons |
| `rules/language-terminology.md` | A9 | Aturan bahasa harus konsisten di setiap respons |
| `skills/anti-hallucination-reasoning/` | A3 | Situasional — relevan saat ada klaim faktual |
| `skills/controlled-assumption-clarification/` | A5 | Situasional — hanya saat prompt ambigu |
| `skills/context-compression/` | A6 | Situasional — hanya saat command `EXECUTE CONTEXT COMPRESSION` |
| `skills/action-recommendation-transparency/` | A8 | Situasional — saat ada aksi/rekomendasi |
| `skills/coding-execution-standards/` | B1–B4 | Situasional — hanya saat task coding |
| `skills/skill-self-evolution/` | B5 | Situasional — hanya setelah task kompleks terverifikasi |

## Instalasi Rules

**Kalau Chief pakai Antigravity 2.0 (IDE dengan panel Agent Manager):**

Cara file-based (direkomendasikan, bisa di-commit ke Git dan dipakai tim):
```
<workspace-root>/.agents/rules/core-identity-anti-sycophancy.md
<workspace-root>/.agents/rules/privacy-anonymity.md
<workspace-root>/.agents/rules/response-structure.md
<workspace-root>/.agents/rules/language-terminology.md
```
Cukup salin folder `rules/` ke `.agents/rules/` di root project Chief — frontmatter `trigger: always_on` di tiap file sudah otomatis dibaca Antigravity sebagai instruksi yang selalu dimuat.

Cara UI (alternatif, per-file, tanpa Git):
Agent icon (sidebar kiri) → Customizations → tab Rules → **+ Workspace** → Activation Mode: **Always On** → tempel isi file (tanpa bagian frontmatter `---`) → Save. Ulangi untuk keempat file.

**Kalau Chief pakai Antigravity CLI (`agy`):**
CLI ini membaca satu file datar `GEMINI.md` atau `AGENTS.md` di direktori aktif (bukan folder `.agents/rules/`). Gabungkan isi keempat file `rules/*.md` (tanpa frontmatter) ke satu `GEMINI.md`, dipisah per bagian `##`. Untuk berlaku di semua project: `~/.gemini/GEMINI.md`.

> Kedua jalur (2.0 vs CLI) berbagi platform agent yang sama tapi punya lokasi konfigurasi yang didokumentasikan berbeda — cek dulu versi mana yang Chief pakai sebelum memilih jalur di atas.

## Instalasi Skills

- **Workspace** (khusus satu project): salin folder `skills/*` ke `<workspace-root>/.agents/skills/` (default terbaru; `.agent/skills/` singular masih didukung untuk kompatibilitas versi lama).
- **Global** (lintas semua project — direkomendasikan untuk paket Chief karena sifatnya bukan spesifik satu project): salin ke `~/.gemini/antigravity/skills/`.

Tidak perlu trigger manual — agent membaca `name`+`description` tiap skill di awal sesi, dan otomatis memuat isi penuh `SKILL.md` saat tugas Chief cocok dengan salah satu description. Setelah menyalin skill baru, mulai sesi/percakapan baru agar Antigravity mendeteksi ulang daftar skill.

## Catatan
File di `rules/` sengaja tidak memakai frontmatter `name`/`description` ala Skill — format Rules Antigravity memakai `trigger:` (`always_on | glob | model_decision | manual`), bukan mekanisme deteksi berbasis description.
# super-agent-powers
