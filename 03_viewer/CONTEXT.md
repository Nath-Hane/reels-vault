# Stage 03: Standalone Viewer Generation

## Stage Identity
- **Stage ID**: 03_viewer
- **Purpose**: Compile structured entries from `index.md` into a zero-dependency, offline HTML search interface (`vault.html`).

---

## Inputs Table

| Context Layer | File / Location | Description |
|---|---|---|
| **Layer 3 (Reference)** | `GLOBAL_IDENTITY.md` | Single-file offline HTML constraints |
| **Layer 4 (Working)** | `index.md` / `02_indexing/output/index.md` | Structured video entries & themes from Stage 02 |

---

## Process

1. Parse all entries from `index.md`.
2. Generate single-file `vault.html` incorporating:
   - Full data payload embedded in JS objects.
   - Real-time search bar filtering across title, content, author, and themes.
   - Interactive theme filter buttons with entry counts.
   - Mobile-responsive layout.
   - Zero external CSS/JS network dependencies.
3. Save output to `vault.html` (and `03_viewer/output/vault.html`).

---

## Outputs

- `vault.html` (and `03_viewer/output/vault.html`): Offline-ready interactive web dashboard.

---

## Human Review Gate
Open `vault.html` in browser:
- Test instant search filtering and theme buttons.
- Confirm links to original Instagram/TikTok posts work correctly.
