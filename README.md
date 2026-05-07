# Core Gym Design

Shared design tokens and patterns for all Core Gym surfaces — member-app, homepage, kassa, signup, eventually Soneli.

**Status:** v0.1, opt-in. Lives alongside Luxe Noir in member-app — not a replacement yet.

## What's here

```
clean/
  tokens.css      ← CSS variables: colors (dark+light), fonts, spacing, radius, motion
```

## Who consumes it

| Repo | How | File |
|------|-----|------|
| `member-app` | Nuxt alias `@coregym-design` | `app/pages/design-system.vue` |
| `homepage` | (not yet — same alias pattern when added) | — |

## Adding a new consumer

In the consumer's `nuxt.config.ts`:

```ts
import { fileURLToPath } from 'node:url'

export default defineNuxtConfig({
  alias: {
    '@coregym-design': fileURLToPath(new URL('../coregym-design', import.meta.url)),
  },
})
```

Then in any CSS file (or Vue scoped style):

```css
@import '@coregym-design/clean/tokens.css';
```

Wrap your root element with `class="clean"` to opt in. Add `light` for light mode.

## Live styleguide

`member.coregym.club/design-system` — visual reference for all tokens and patterns. Source: `member-app/app/pages/design-system.vue`.

## Adding tokens

Edit `clean/tokens.css` directly. All consumers reload via Vite HMR. Keep variable names prefixed `--clean-*`.
