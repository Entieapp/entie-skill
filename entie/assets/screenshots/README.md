# Screenshots

This folder holds visual references for Entie — actual app screenshots that Claude can look at when visual context matters (UI explanations, design feedback, App Store visuals, support replies that reference specific screens).

## Folder layout

```
screenshots/
├── README.md                ← you are here
├── features/                ← one folder per feature, mirroring /features/
│   ├── cycle-tracking/
│   ├── couple-questions/
│   ├── ai-chat/
├── onboarding/              ← signup, partner connection flow, first-run screens
└── ui-elements/             ← isolated components (buttons, icons, cards, modals)
```

## Naming convention

Use lowercase, kebab-case, descriptive. Pattern:

```
<feature>-<screen-or-state>.png
```

**Good examples:**
- `cycle-tracking-main-screen.png`
- `cycle-tracking-analytics-regular.png`
- `ai-chat-deep-talk-three-scenarios.png`
- `ai-chat-guided-space-empty.png`
- `couple-questions-waiting-for-partner.png`
- `onboarding-partner-invite-sent.png`

**Bad examples:**
- `Screenshot 2026-05-25 at 14.22.png` (default OS name — rename it)
- `IMG_1234.PNG` (no context)
- `cycle.png` (too vague)

## Formats

- **`.png`** preferred for screens — lossless, sharp text
- **`.jpg`** acceptable for marketing-style mockups where size matters
- **`.svg`** for icon assets if you have them
- **Avoid `.heic`** — convert to PNG first; not universally supported

## Sizing

Keep file sizes reasonable. If a screenshot is over **2 MB**, downscale or compress before committing. The repo will get heavy fast otherwise.

A rough target: each PNG under **500 KB** when possible. Tools like [TinyPNG](https://tinypng.com/) or `pngquant` handle this cleanly.

## What to capture per feature

For each feature, aim for these states:

1. **Main / default state** — what the user sees on first open
2. **Filled / active state** — with real data populated
3. **Empty state** — before any data exists (if relevant)
4. **Edge state** — error, partner-not-connected, partner-hasn't-answered, etc.

Not every feature needs all four. Use judgment.

## Adding a folder for a new feature

When a new feature is added under `/features/`, mirror it here:

```bash
mkdir assets/screenshots/features/<new-feature-name>
```

Then drop screenshots in following the naming convention above.

## Linking from feature files

Each feature `.md` file can reference its screenshots. Example pattern (in `features/cycle-tracking.md`):

```markdown
## Screenshots

- Main screen: `../assets/screenshots/features/cycle-tracking/cycle-tracking-main-screen.png`
- Analytics: `../assets/screenshots/features/cycle-tracking/cycle-tracking-analytics.png`
```

When Claude has access to these files (e.g., when the skill is loaded with images), it can view them directly to ground its understanding in the actual UI.

## Privacy note

Make sure screenshots **do not contain real user data** — no real names, real partner names, real cycle dates tied to a real person, or anything else identifying. Use test accounts or scrub data before committing.
