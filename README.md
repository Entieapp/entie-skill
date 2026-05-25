# Entie Skill

A Claude skill that gives Claude full knowledge of **Entie**, a mobile Couple Assistant app — its positioning, brand voice, features, target audience, and copywriting examples.

When this skill is installed, Claude can help you write Entie marketing copy, App Store descriptions, customer support replies, social posts, feature explanations, and any other Entie-facing content — all in the correct voice and within the brand's guardrails.

**Website:** https://www.entie.app/

---

## Installation

### Option 1 — Install in Claude.ai (recommended)

1. **Download the latest `.skill` file:**

   👉 [**Download entie.skill**](https://github.com/Entieapp/entie-skill/releases/latest/download/entie.skill)

   This link always points to the most recent release.

2. Open **Claude.ai** → **Settings** → **Capabilities** → **Skills**

3. Click **Upload skill** and select the downloaded file.

4. Done. Claude will now use the Entie skill whenever it's relevant.

### Option 2 — Install a specific version

If you want a specific version (e.g. for rollback or testing), grab it from the [Releases page](https://github.com/Entieappentie-skill/releases) and follow the same upload steps.

### Option 3 — Use locally (Claude Code / API)

Clone the repo and point your tools at the `entie/` folder:

```bash
git clone https://github.com/Entieapp/entie-skill.git
```

The skill folder is everything inside `entie/` (SKILL.md plus subfolders).

---

## Updating

To update to the latest version:

1. Download the file again from the same link above.
2. Re-upload it in **Settings → Capabilities → Skills**.
3. Claude will replace the existing version.

Check the [CHANGELOG](CHANGELOG.md) to see what changed.

---

## What's inside

```
entie/
├── SKILL.md                  ← entry point Claude reads first
├── brand/                    ← positioning, values, voice, USP, audience, guardrails
├── features/                 ← one file per product feature
├── examples/                 ← copywriting reference (taglines, App Store, support, social)
└── assets/screenshots/       ← visual references organized by feature
```

Each folder has its own `README.md` explaining what's inside and how to add to it.

---

## Contributing

This skill is designed to be modular — most updates touch one file at a time.

**Common updates:**

- **New feature shipped?** Add a file in `entie/features/` and reference it in `entie/features/README.md`.
- **Voice update?** Edit `entie/brand/voice-and-tone.md`.
- **New great support reply?** Add it to `entie/examples/support-replies.md`.
- **New screenshots?** Drop them in the matching `entie/assets/screenshots/features/<feature>/` folder.

After committing changes, bump the version in `entie/SKILL.md` (if you use one) and tag a release to ship updates to users.

---

## Releasing a new version

(For maintainers.)

1. Update `CHANGELOG.md` with the new version and what changed.
2. Commit and push.
3. Package the skill (zip the `entie/` folder, rename to `entie.skill`):

   ```bash
   cd entie-skill
   zip -r entie.skill entie/
   ```

4. Create a new GitHub release with tag `v<X.Y.Z>` and attach `entie.skill`.
5. Users following the install link automatically get the new version.

---

## License

Not yet specified.
