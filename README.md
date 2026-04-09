# UXLens

**AI-powered UX audits from a screenshot or URL — in seconds.**

UXLens is a single-file web app that runs structured UX audits using Claude API. All you have to do is paste a URL or upload a screenshot and get a detailed breakdown of what's working, what isn't, and exactly how to fix it. I've built the audit output to provide separate callouts for designers and developers.

I built this as a portfolio project to explore the intersection of UX methodology and AI tooling.



---

## What it audits

Each analysis covers six categories:

| Category | What it looks at |
|---|---|
| **Clarity** | Is the purpose of the page immediately obvious? |
| **Visual Hierarchy** | Does the layout guide the eye to what matters? |
| **Trust Signals** | Does the UI feel credible and safe? |
| **Transparency** | Does the product communicate honestly about what it does and how? |
| **Accessibility** | WCAG compliance, contrast ratios, keyboard/screen reader considerations |
| **Feedback Loops** | Does the UI respond to user actions in meaningful ways? |

> **Why both Trust Signals and Transparency?** These are often collapsed into one when, in actuality, they're pretty distinct. Trust is about perception (does this *feel* safe?), whereas transparency is about honesty (does this *tell the truth*?). A dark pattern can score high on trust, but zero on transparency. UXLens keeps them separate on purpose.

Each category returns two layers of callouts:
- **Designer callouts** — Framing, layout, copy, and UX pattern recommendations
- **Developer callouts** — Concrete fixes with CSS properties, hex codes, contrast ratios, and WCAG references

---

## How to use it

UXLens uses a bring-your-own-key model. You'll need a Claude API key from Anthropic.

1. Get a free API key at [console.anthropic.com](https://console.anthropic.com)
2. Open the app and paste your key into the key field (it stays in your browser session only — never stored or sent anywhere except Anthropic's API)
3. Upload a screenshot or paste a URL
4. Read your audit

---

## Stack

- **Single HTML file** — no build step, no dependencies, no framework
- **Claude API** (`claude-sonnet-4-20250514`) for structured audit generation
- **Fraunces** (headings) + **DM Mono** (UI) as the type system
- CSS custom property design system: `--paper`, `--ink`, `--accent`, `--good`, `--warn`, `--bad`


---

## Design decisions worth noting

- **No backend** — Keeping this as a single file was a deliberate constraint to prove the concept is as lean as possible
- **BYOK** — Putting API key management in the user's hands keeps costs transparent and the architecture honest
- **Six audit categories** — I chose to cover the full UX surface area, careful not to run into any redundancy in the results
- **Dual callout layers** — I noticed most audit tools speak only to one audience. Separating designer and developer output makes the results actually actionable for both!

---

## About

Made by **Jo Kamau** — UX designer exploring AI-augmented design tooling.

[LinkedIn](https://www.linkedin.com/in/njokikamau/) · [Portfolio](https://www.njokikamau.com/)
