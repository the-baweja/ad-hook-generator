# Ad Hook Generator — Scroll-Stopping Hooks for Meta Ads

**Generate 30+ scored ad hooks through a 6-step research-to-hooks pipeline with 51 frameworks (20 copy + 31 visual).**

Give Claude a brand name and it researches the product, audits competitor hooks in the Meta Ad Library, mines customer language for scroll-stopping phrases, matches the right frameworks to the right angles, writes 30–50 hooks, and scores each one on a 6-factor rubric with predicted hook-rate ranges. Every hook traces back to real research — not guesswork.

## Install

**Claude Desktop (Cowork):** download [`ad-hook-generator.skill`](https://github.com/the-baweja/ad-hook-generator/releases/latest) → Settings → Skills → drop it in.

**Claude Code:**
```
git clone https://github.com/the-baweja/ad-hook-generator.git ~/.claude/skills/ad-hook-generator
```

**Manual:** clone this repo into any skills directory your Claude setup reads from.

## What it does

You give it a brand or product name. It runs a 6-step pipeline:

1. **Brand & Audience Research** — researches the brand, its customers, their pain points, and identifies 3–5 ad-worthy angles
2. **Competitor Hook Audit** — pulls competitor ads from the Meta Ad Library and maps which hook types are oversaturated vs. underused
3. **Customer Language Mining** — extracts scroll-stopping phrases, specific numbers, and emotional triggers from reviews, Reddit, and social comments
4. **Framework Matching** — maps angles to the best hook frameworks (51 total: 20 copy + 31 visual), weighted by competitive gaps and format suitability
5. **Hook Generation** — writes 30–50 hooks across two formats:
   - 🖼️ **Static hooks** — short / medium / long text variations for image ads and primary text
   - 🎬 **Video hooks** — visual + audio + text overlay + camera direction for the first 0–3 seconds
   - 🖼️🎬 **Both** — hooks that adapt to either format with notes
6. **Scoring & Ranking** — scores every hook on pattern interrupt strength, specificity, emotional charge, audience match, proof embedded, and format fit — with predicted hook-rate ranges

Works **fully standalone**. If you've already run the Competitor Ad Spy, Ad Angle Generator, or Audience Pain Point Miner, it imports their outputs as a shortcut — but it doesn't need them.

## Output

**Branded DOCX report** containing:

- How to Read This Library (format guide for static vs. video hooks)
- Research summary (brand, audience, angles, pain points — organized by step)
- Hook-rate prediction methodology (6-factor rubric explanation)
- Top 10 Priority Hooks (highest-scoring, ranked by composite score)
- Full Hook Library (all 30+ hooks organized by framework type)
- Testing Roadmap (Wave 1/2/3 structure, kill/iterate/scale thresholds)
- Framework Coverage Map (which frameworks were used and why)

## Customize Your Branding

Edit `references/branding.md` with your own brand colors, typography, and document structure. The skill reads this file to generate reports that match your brand identity.

## Example

Prompt:
```
Generate ad hooks for AG1 (Athletic Greens).
Format: video and static.
Funnel stage: cold traffic.
```

Output: 35 hooks generated across 19 frameworks, scored 2.3–4.7 on the 6-factor rubric. Top hook predicted at 35–50% hook rate. Includes 21 static hooks with 3 length variations each, 14 video hooks with full production specs.

## Who this is for

Media buyers, creative strategists, brand owners, and performance marketers who want a systematic hook library instead of staring at a blank screen.

This is skill 4 of 10 in the **AI Skills for Media Buyers** series by [Baweja Media](https://bawejamedia.com).

---

## Want Baweja Media to audit your ad account and explore opportunities to work together?

[→ Book a strategy call](https://webinar.sannidhyabaweja.com/vsl-lp-ind)

---

Built by [Baweja Media](https://bawejamedia.com) · MIT License
