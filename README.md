# Mascot Camp 2026 — Dom & Wyatt (Command Center)

A single-page, self-contained static site with everything Dom and Wyatt need to get **to** and **through** Keystone Mascots Camp — **Hersheypark All-American Mascot Day + Millersville University, PA, July 9–12, 2026.**

Built from the Keystone Mascots / Hersheypark emails, the family Task Board, and keystonemascots.com.

## What's inside

```
mascot-camp-2026-hub/
├── index.html                     ← the whole site (open this)
├── README.md                      ← you are here
├── HANDOFF.md                     ← exact commands to push to GitHub + turn on Pages
├── .gitignore
└── assets/
    ├── img/
    │   ├── wyatt-mascot.png        ← Wyatt's mascot art (hero image)
    │   └── parking-map.png         ← Hersheypark parking map (shown inline)
    └── documents/
        ├── Parking-Map.pdf         ← Hersheypark parking map (GATESIDE / Lot N)
        ├── Lunch-Order-Wyatt.pdf   ← submitted Hershey lunch order
        ├── Lunch-Order-Dom.pdf
        └── README.md
```

Everything is a single `index.html` with inline CSS/JS and **relative** asset paths, so it works three ways with no build step:

- Double-click `index.html` to open locally.
- Serve locally: `python3 -m http.server` in this folder, then visit `http://localhost:8000`.
- Deploy to **GitHub Pages** (see `HANDOFF.md`). Relative paths mean it works at `https://<user>.github.io/mascot-camp-2026-hub/` too.

## Privacy — read before publishing

This folder is a **self-contained repo root**. It contains **no** personal/legal documents on purpose:

- ✅ Included (safe): the itinerary, schedule, packing list, contacts, lunch-order PDFs, and Wyatt's mascot art.
- ❌ **Excluded**: signed Hersheypark waivers, PA/FBI background clearances, and the registration packet. Those contain signatures and personal identifiers and stay in `Kids\Wyatt\Mascot\` — never commit them.

If you push this to GitHub, anything committed here can become public via Pages. The content here is safe to publish, but a **private repo is still recommended**. GitHub Pages on a **Free** plan requires a **public** repo; private-repo Pages needs a paid plan (see `HANDOFF.md`).

## Updating it

It's just HTML — edit `index.html` and re-open. The **parking map** is already bundled and shown inline. To add the Hersheypark **parking pass** too, save that PDF (from Erin's July 3 email) into `assets/documents/` and link it in the Documents section — and keep the repo private if you do.
