# Notice

## This project

Caveman (improved edition)
Modifications Copyright 2026 Zaki (@zakiuhh)

Not affiliated with or endorsed by the original author.

## Original work

**Project:** caveman, https://github.com/JuliusBrussee/caveman
**Author:** Julius Brussee
**License:** MIT (the skill; see the full text in `LICENSE`)

This edition is based on the original caveman skill (`SKILL.md`, intensity levels, and the Auto-Clarity idea come from there). Later versions of the upstream repository are licensed differently; this edition is derived from the MIT-licensed skill.

## Changes in this edition

- **Rewrote the workflow** in `SKILL.md`: turn-on step, a repeatable per-reply procedure (answer first, compress, accuracy check, clarity check, drift check), level switching with a clear ladder, and an explicit stop rule.
- **Added an accuracy check** that protects negations, numbers, versions, identifiers, and step order from being lost in compression, and a rule to keep real uncertainty instead of hiding it.
- **Expanded Auto-Clarity** (security, destructive actions, risky sequences, high-precision topics, confused users) and added a clear "Boundaries" list of what is always written normally.
- **Added edge cases**: detail requests, lists and tables, ambiguous requests, conflicting style requests, and other languages.
- **Fixed the wenyan examples** (mixed-language fragments) and removed unverified savings figures.
- **Added** `references/examples.md` with more worked examples, plus the logos, README, and this notice.
