# Changelog

All notable changes to the Entie skill will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Versioning rules

- **MAJOR** (X.0.0) — breaking changes to how the skill works (e.g., renamed core files, restructured folders that would break existing references).
- **MINOR** (1.X.0) — new features, new examples, new sections; backward-compatible additions.
- **PATCH** (1.0.X) — fixes to existing content, typos, small clarifications, screenshot updates.

---

## [1.1.0] — 2026-10-03

### Added
- Relationship Health Score feature (`features/relationship-health-score.md`): inputs (three check-in questions + internal signals), use on the Dashboard and via MCP for the AI service, and the full 0–100 range descriptions.
- Measurement cadence: the three questions are re-asked every 30 days; between measurements the score decreases by 0.2 points per day.
- Notifications: renamed the `Dev Status` column to `Status` to match the sheet and added `In progress` as a possible status value.

## [1.0.3] — 2026-09-30

### Added
- Updated the daily tip feature. How it works, etc.
- Added Google Sheet connector. Now the skill can read app notifications.

## [1.0.2] — 2026-08-27

### Added
- Added a separate [mobile app changelog](entie/MOBILE_APP_CHANGELOG.md) for Entie releases on the App Store and Google Play.

## [1.0.1] — 2026-05-25

### Added
- Added app logo

## [1.0.0] — 2026-05-25

### Added
- Initial release of the Entie skill.
- Brand documentation (`brand/`):
  - Position statement
  - Core values (Honesty, Transparency, Service Maximization, Privacy-focused, Individuality)
  - Brand voice & tone with full spectrum scoring
  - USP and usage rules
  - Target audience (ages 26–44, three core pain points, six segments)
  - Guardrails (medical, mental health, sexual content, relationship advice, privacy, gender)
- Feature documentation (`features/`):
  - Cycle Tracking (shared by both partners)
  - Daily AI Tip
  - Daily Logging
  - Couple Questions (synced reveal)
  - AI Chat — three modes (Simple Chat, Deep Talk, Guided Space)
  - Life Stage Modes (Cycle, Pregnancy, Menopause)
  - Partner Connection
- Copywriting examples (`examples/`):
  - Taglines
  - App Store / Play Store copy
  - Customer support reply templates
  - Social media examples
- Screenshot folder structure (`assets/screenshots/`) with placeholder READMEs for each feature, onboarding, and UI elements.
- GitHub installation instructions via Releases.
