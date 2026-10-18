# ⚔️ Signal Drift — Shadow Blade

A fast arcade action game in a **single HTML file**. You are the shadow blade:
cut down what you can, dodge what you can't, and carve through **100 levels**
of falling chaos. No installs, no build step, no dependencies — open it and play.

**Play it here:** https://zidan-7-alive.github.io/signal-drift/

---

## How to play

| Input | Action |
|---|---|
| **Touch + drag** | Floating joystick appears under your thumb — steer the blade |
| **Arrow keys / WASD** | Move (desktop) |
| **Mouse hover** | Aim (desktop) |

Your **blade tip cuts anything it touches** — kills build a **combo multiplier (up to ×10)**.
Getting hit resets it.

- **Clear a level:** destroy the required number of enemies (`12 + 2 × level`)
- **3-star objectives** per level: collect the green signals, destroy the featured
  enemy type, finish untouched — clearing a level unlocks the next
- **Lives:** 3 per run (4 with the shop upgrade) — hearts drop when you're hurt

### Know your enemies

| Enemy | Behavior |
|---|---|
| Rock / Ember / Shard / Bolt / Comet / Dart | Cut freely — each with its own motion |
| **Void orb** | Slowly homes toward you |
| **Meteor** | Takes **2 hits** to cut |
| **Ghost** | Only cuttable **while visible** |
| **Spiker** | ⚠️ **Cannot be cut — dodge only** |
| **Boss** (every 10th level) | Health bar, sweeps the top of the screen, fires dart volleys |

### Pickups

- **Green signal** — +25 points (collect enough for stars)
- **Amber charge** — 8s blade overcharge: longer reach, double kill points, body contact shreds
- **Pink heart** — +1 life (up to your max)

### Systems

- **Shop** — banked gems buy: longer blade (3 tiers), +1 starting life, gem magnet (3 tiers), and **5 sword skins** (Shadow, Bloodmoon, Frost, Gilded, Void)
- **Perks** — every 5 levels, pick 1 of 3 random perks (combo window, charge duration, slower enemies, magnet, gem value, +1 life). Lasts until game over
- **Daily challenge** — a seeded level, identical for every player each day, with its own best score, share button, and a streak counter (gem bonuses at 3 and 7 days)
- **Endless mode** — unlocked after level 100; difficulty ramps forever, separate high score
- **Near-miss bonus** — skim within ~10px of an enemy for extra points

## Run it locally

Just open with link in any browser or download apk. Works offline, saves progress to
`localStorage`.

## Deploy your own copy (GitHub Pages)

1. Fork or create a repo named **`<username>.github.io`** (or any repo, served from `gh-pages` / root)
2. Upload `index.html` to the repo root (**Add file → Upload files**)
3. Settings → Pages → source: **Deploy from branch** → `main` / `/ (root)`
4. Wait a minute, visit your URL. Done — every future update is just re-uploading `index.html`

## Tech notes

- One self-contained HTML file — canvas rendering, Web Audio synth SFX + music loop, zero assets, zero network calls
- **Game Manager** module (embedded) centralizes all save state: `current_level`, `unlocked_levels`, `banked_gems`, `longer_blade_tier`, `extra_lives_unlocked`, `gem_magnet_tier`, `unlocked_sword_skins` — versioned, sanitized, and migrating from older saves automatically
- Swept-segment collision (no tunneling at high speeds), theme-aware palette, reduced-motion support, vibration + screen-shake feedback

## Roadmap ideas

- Real ad network integration (slots are already designed in)
- More enemy types & boss patterns past level 100
- Leaderboards for the daily challenge

---

Made with canvas, caffeine, and an irresponsible number of prototypes. 🐒
