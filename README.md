# AppADay 073 — Explain It Three Ways

Type any concept and it refracts into three explanations at once, each tuned to who is listening: a warm, analogy-driven version for a child, a plain-language version for a curious friend, and a precise, technical one for an expert. A follow-up question re-runs all three together so you can steer the whole set at once.

**Category:** E (Educational) · **AI-powered:** yes (Claude API)
**Live:** https://augustineiacopelli.github.io/appaday-073-three-ways/

## What it does

One idea in, three focal depths out. Each panel has its own headline, a full explanation written at the right register, and a level-specific note:

- **For a child** — everyday words, short sentences, and a concrete "Picture this" analogy.
- **For a peer** — the dinner-table explanation, with a "Where you meet it" line for real-world context.
- **For an expert** — the mechanism stated precisely, plus "The subtle part": one edge case or common misconception practitioners care about.

Try the example chips, or type your own. Recent concepts are remembered locally so you can revisit them in a tap. The "Sharpen all three" follow-up takes a request like "focus on the money side" and re-explains the concept at every level with that lens.

## Design

Built around a **prism** metaphor: one concept enters and disperses into three. A deep indigo-slate study background, light reading cards, and three spectral accents that encode the levels rather than decorate them — amber for the child (a wide beam), teal for the peer, violet for the expert (fine detail). A spectrum thread visually splits the concept into the three columns, which disperse into view in sequence on generate. Fraunces sets the wordmark and headlines; Inter carries the explanation bodies and UI.

## Technical

- Single-file vanilla HTML, CSS, and JavaScript. No frameworks, no build step.
- Google Fonts (Fraunces, Inter) via CDN; no other external dependencies.
- Direct browser-to-Anthropic API calls with `anthropic-dangerous-direct-browser-access: true`.
- `const CLAUDE_MODEL = 'claude-sonnet-5'` default; model selectable in Settings.
- Structured JSON response parsed into the three panels; all model text rendered via `textContent`.
- API key and model live only in the Settings (⚙️) modal, stored in `localStorage`, never committed to source.
- Responsive from a 375px phone up through desktop; keyboard focus visible; reduced motion respected.

## Setup

1. Open the app and click the gear (⚙️).
2. Paste your Anthropic API key (stored only in your browser) and pick a model.
3. Type a concept and press Explain.

---

Part of [AppADay](https://augustineiacopelli.github.io/appaday/) — one app, every day.
