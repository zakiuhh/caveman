<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.png">
    <source media="(prefers-color-scheme: light)" srcset="assets/logo-light.png">
    <img alt="Caveman logo" src="assets/logo-light.png" width="140">
  </picture>
</p>

<h1 align="center">Caveman</h1>

<p align="center">
  A Claude skill that makes replies short and sharp: fluff dies,
  technical substance stays.
</p>

---

## What it does

Turn it on and Claude answers like a smart caveman: no filler, no pleasantries, no hedging for show, straight to the answer. Code, numbers, error messages, and technical terms stay exact. When something is risky, it drops back to plain, careful sentences, then carries on.

> **Normal:** "Sure! I'd be happy to help. The issue you're experiencing is likely caused by..."
> **Caveman:** "Bug in auth middleware. Token expiry check use `<` not `<=`. Fix:"

## Turn it on and off

| Say | Result |
|---|---|
| `/caveman`, "caveman mode", "talk like caveman", "be brief", "fewer words" | On (level: full) |
| `/caveman lite` / `full` / `ultra` | Choose a level |
| `/caveman wenyan-lite` / `wenyan-full` / `wenyan-ultra` | Classical Chinese levels |
| "shorter", "more compressed" | One step tighter |
| "less terse", "more detail", "clearer" | One step looser |
| "stop caveman", "normal mode" | Off |

The level stays until you change it or the chat ends.

## Levels

| Level | What changes |
|---|---|
| **lite** | No filler or hedging. Keeps articles and full sentences. Professional but tight. |
| **full** | Drops articles, fragments OK, short synonyms. Classic caveman. *(default)* |
| **ultra** | Abbreviations (DB, auth, fn, req, res), arrows for causality, one word when one word is enough. |
| **wenyan-lite** | Semi-classical Chinese: no filler, grammar intact. |
| **wenyan-full** | Fully classical, maximum terseness. |
| **wenyan-ultra** | Extreme abbreviation with a classical feel. |

Example: "Why does my React component re-render?"

| Level | Reply |
|---|---|
| lite | "Your component re-renders because you create a new object reference on each render. Wrap it in `useMemo`." |
| full | "New object ref each render. Inline object prop = new ref = re-render. Wrap in `useMemo`." |
| ultra | "Inline obj prop → new ref → re-render. `useMemo`." |

## How it works

Every reply follows the same short loop:

1. **Answer first**, no preamble
2. **Compress** to the current level
3. **Accuracy check**: negations, numbers, versions, names, step order, and code survive
4. **Clarity check**: risky topics get plain sentences
5. **Drift check**: no slipping back into filler over a long chat
6. **One next step**, if there is one

## Stays careful where it matters

Caveman drops itself automatically for security warnings, destructive actions (delete, drop, force-push, overwrite), risky multi-step sequences, high-precision topics (medical, legal, financial), and when you seem confused. It keeps real uncertainty ("Unsure. Check Node version.") instead of turning it into a confident fragment.

Code, code comments, commit messages, PR descriptions, documents, and anything you'll send to other people are always written normally.

## Install

### Claude (web and apps)

1. Download this repo as a ZIP (or zip the `caveman` folder yourself). Make sure `SKILL.md` sits at the top level of the folder inside the ZIP.
2. Open Claude's settings and find the Skills section.
3. Upload the ZIP and turn the skill on.

### Claude Code

```bash
git clone https://github.com/zakiuhh/caveman.git
cp -r caveman ~/.claude/skills/
```

(Change the clone URL if your repo lives somewhere else.)

## Repo structure

```
caveman/
├── assets/
│   ├── logo-dark.png      # for dark backgrounds
│   └── logo-light.png     # for light backgrounds
├── references/
│   └── examples.md        # more worked examples
├── LICENSE                # MIT
├── NOTICE.md              # credits and list of changes
├── README.md
└── SKILL.md               # the actual skill
```

## Customizing

Everything lives in `SKILL.md`. Tune the drop and keep lists, the level definitions, or the Auto-Clarity cases to your taste. Keep the `name` in the frontmatter the same as the folder name.

## Credits and license

Based on the original **caveman** skill by Julius Brussee ([JuliusBrussee/caveman](https://github.com/JuliusBrussee/caveman)), MIT licensed. This edition adds a clearer workflow, accuracy checks, and more examples. See [LICENSE](LICENSE) and [NOTICE.md](NOTICE.md). Not affiliated with or endorsed by the original author.
