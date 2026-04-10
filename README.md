# Dine In Together 🍽️

> AI-powered group food ordering app — built with zero prior coding experience using Claude as a co-builder.

**Live app:** [tejasvipk.github.io](https://tejasvipk.github.io)

---

## What it does

Dine In Together solves a real everyday problem: coordinating food orders for a group is slow, nobody remembers each other's preferences, and someone always ends up unhappy.

The app introduces **Circles** — named groups of people who order food together. The organiser picks a meal type, the AI suggests restaurants ranked by how well they match the whole group's preferences, everyone votes, and the most-voted restaurant wins. The AI then predicts what each person is most likely to order based on their history.

---

## Key features

| Feature | Description |
|---|---|
| **Circle management** | Create multiple circles (Family, Work, Friends) and switch between them via a dropdown |
| **Meal type selector** | Choose Breakfast, Lunch, Dinner, Snacks, Midnight munchies, or Cravings |
| **AI restaurant suggestions** | Claude API generates 2–3 options ranked by group preference match score |
| **Real-time voting** | Circle members vote and cards re-rank live by most votes |
| **Order prediction engine** | Claude predicts each person's most likely dish based on their order history |
| **AI preference suggestions** | AI surfaces patterns from order history as approve/skip cards |
| **Favourites** | Order anyone's saved favourite dish directly — no voting needed |
| **Payment split** | Choose between organiser pays full bill or automatic equal split |
| **Insights tab** | Bar chart of group preferences + individual radar taste profiles |
| **Privacy-first invites** | Members see a clear consent notice before their preferences are shared |

---

## How the AI works

All AI features are powered by the **Anthropic Claude API** (Haiku model):

**Restaurant suggestions** — Claude receives all circle members' preference profiles and the selected meal type, then returns 3 ranked restaurant options with cuisine, timing, price, star rating, match score, and a plain-language reason why it suits the group.

**Order prediction** — When a restaurant is selected, Claude analyses each person's full dish history and predicts their most likely order. Predictions appear pre-filled with an "AI predicted" badge.

**Preference suggestions** — After manual preferences are set, Claude scans order history to surface patterns the user hasn't explicitly stated, presented as individual approve/skip cards.

The prediction engine is not a traditional trained ML model — it uses Claude's language reasoning to pattern-match across order history, achieving the same outcome as a collaborative filtering recommendation system with a fraction of the complexity.

---

## Tech stack

- **Frontend:** HTML, CSS, vanilla JavaScript — single file, no framework
- **AI:** Anthropic Claude API (`claude-haiku-4-5`)
- **Charts:** Chart.js (bar + radar)
- **Hosting:** GitHub Pages (free, zero backend)
- **Data:** Client-side only — sessionStorage for API key, JS objects for app state

---

## Running it locally

1. Clone the repo:
   ```bash
   git clone https://github.com/tejasvipk/tejasvipk.github.io.git
   ```
2. Open `index.html` in your browser
3. Click **"Suggest different options"** or **"Finalize order"**
4. Enter your [Anthropic API key](https://console.anthropic.com) when prompted

The key is stored in `sessionStorage` only — it is never written to the codebase or committed to GitHub.

---

## Project structure

```
tejasvipk.github.io/
└── index.html        # Complete app — all HTML, CSS, and JS in one file
```

---

## What I learned building this

This project was built from **zero coding background** using Claude as a co-builder and teacher. Key things I learned:

- How to structure a single-page app with tab-based navigation
- How to call an external API from the browser using `fetch`
- Why API keys must never be stored in public code — and how to handle them safely via sessionStorage
- How to use an LLM as a reasoning engine for prediction tasks instead of building a traditional ML pipeline
- How GitHub Pages turns a repository into a live website instantly

---

## Future roadmap

- [ ] Real restaurant API integration (Google Places / Yelp)
- [ ] Backend + database for persistent data across sessions (Supabase)
- [ ] Real payment splitting via Stripe or Splitwise
- [ ] Push notifications when the organiser starts an order session
- [ ] Native mobile app (React Native)

---

## Author

**Tejasvi** — ServiceNow | AI learner | Building in public

- GitHub: [@tejasvipk](https://github.com/tejasvipk)
- Live project: [tejasvipk.github.io](https://tejasvipk.github.io)

---

*Built as part of a personal AI learning curriculum — demonstrating practical AI integration, product thinking, and the ability to ship real working software.*
