# Adaptive Brain

> GDG UTSC AI Case Competition 2026 · Build with AI · Powered by Google

A browser-based study companion that adapts any academic content to match your learning style. No backend, no installation — runs entirely in your browser as a single HTML file.

**Live demo:** [sewermermaid.github.io/adaptive-brain](https://sewermermaid.github.io/adaptive-brain)

---

## The Problem

The standard way of studying — reading walls of text, memorizing dense notes — is designed for one type of learner. Students with ADHD, ESL students, and auditory learners are left behind by tools that don't adapt to them.

## The Solution

A two-step flow that layers adaptations on top of each other rather than treating them as separate silos:

**Step 1 — Optional ESL simplification**
Toggle on to rewrite academic vocabulary into plain English before studying. Complex Latinate words are swapped for simple everyday equivalents while technical terms are preserved. The original and simplified text are shown side by side.

**Step 2 — Choose how to study**

| Mode | Who it's for | How it works |
|------|-------------|--------------|
| 🎧 **Audio Mode** | Commuters, auditory learners | Reads notes aloud with live word-by-word highlighting via Web Speech API. Adjustable speed (0.75×–2×). |
| ⚡ **Focus Mode** | ADHD / focus-seeking students | Chunks content into cards gated behind comprehension questions. Boss question at the end. XP counter. Unlocks real student rewards. |

Both modes operate on whatever came out of Step 1 — so an ESL student with ADHD can simplify first, then study in Focus Mode on the simplified text.

---

## Features

- **No installation** — single `index.html`, open in any modern browser
- **Bring your own key** — supports Gemini, Anthropic, and OpenAI API keys. Keys stored in `localStorage`, never leave your device
- **ESL preprocessing** — AI rewrites academic language into plain English without losing technical terminology
- **Audio playback** — native browser TTS with synchronized word highlighting, no external service required
- **Chunked study flow** — content broken into digestible sections, each gated behind a comprehension check
- **Boss question** — synthesis question at the end of each session requiring deeper understanding
- **XP + rewards** — earn points for correct answers, unlock student discounts (Tim Hortons, Spotify, UNiDAYS, DoorDash, and more)

---

## Tech Stack

- Vanilla HTML/CSS/JS — zero dependencies, zero frameworks
- [Web Speech API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API) — native browser TTS, no external service
- Gemini API (default) / Anthropic Claude API / OpenAI API — ESL simplification + question generation
- GitHub Pages — static hosting

---

## Running Locally

No build step required.

```bash
git clone https://github.com/sewermermaid/adaptive-brain
cd adaptive-brain
open index.html
```

Click the key indicator in the bottom-right corner, select your provider (Gemini recommended), and paste your API key. For Gemini, get a free key at [aistudio.google.com](https://aistudio.google.com) — no credit card required.

---

## Design Decisions

**Why is ESL a preprocessing step, not a separate mode?**
A student who needs language simplification still needs to actually study the content. ESL simplification and study mode (audio or focus) are sequential, not parallel — building them as a pipeline rather than silos reflects how a real student would use them.

**Why no LLM for audio?**
The Web Speech API is built into Chrome, Edge, and Safari. It's instant, offline, and free. An LLM adds latency and cost with no quality benefit for this use case.

**Why deterministic chunking for ADHD?**
ADHD learners benefit from structural intervention, not content rewriting. Enforced gates address the core problem — attention management — more directly than paraphrasing the content.

**Why a rewards system?**
Existing EdTech gamification is cosmetic. Tying XP to real student discounts creates genuine motivation and a viable monetization path without ads or subscriptions.

---

## Roadmap

- [ ] PDF and image upload support
- [ ] UNiDAYS API integration for live reward redemption
- [ ] Spaced repetition scheduling across sessions
- [ ] Vocabulary difficulty slider for ESL mode
- [ ] Progress persistence via localStorage

---

Built for the GDG UTSC AI Case Competition · March 2026
