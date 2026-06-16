# Contributing a theme

Themes are single JSON files of color tokens — small, self-contained, and easy
to review. To add one:

1. **Fork** this repo.
2. Add `themes/<id>.theme.json`. Start by copying an existing theme
   (`themes/nord.theme.json` is a good base) and changing the colors.
3. Fill in the fields:
   - `id` — a lowercase slug, `^[a-z0-9][a-z0-9-]{0,38}$`, matching the file
     name. It can't be `zinc` (the built-in theme).
   - `label` — the name shown in φ's theme picker (≤ 60 chars).
   - `description` — one line for the picker (optional, ≤ 200 chars). If the
     palette is based on an existing project, credit it here.
   - `light` and/or `dark` — maps of `--ps-*` token → CSS color. Prefer shipping
     **both** so the theme works in either Appearance.
4. **Follow the token contract** in the [README](./README.md#themeable-tokens).
   Only listed tokens are read; unknown keys and non-color values are dropped on
   install. Any token you omit falls back to Zinc.
5. **Mind contrast.** Aim for WCAG AA on text against its background. The whole
   point is comfortable long-form writing.
6. **Test it.** Install the file in φ (Settings → Appearance → Install theme…)
   and check both light and dark, the editor, sidebar, wiki links, and a version
   diff.
7. Open a **pull request** with a short description and, ideally, a screenshot.

Keep palettes tasteful and legible — themes that fail basic contrast or are
near-duplicates of an existing one may not be merged.

## Licensing & attribution

By opening a PR you agree your contribution is released under this repo's
[MIT license](./LICENSE). Only submit palettes you created or that you may
redistribute: if a theme adapts an existing project's colors, that project's
license must allow it, and you must add the upstream's license notice to
[`THIRD-PARTY-LICENSES.md`](./THIRD-PARTY-LICENSES.md). Don't use a project's
name in a way that implies official affiliation or endorsement, and never
include third-party logos or trademarks.
