# Round 1: Patch the Pixels

**Client:** BrewLab, a small-batch coffee subscription.
**Situation:** Their landing page was handed over half-finished and a lot is broken. Fix it and finish it before it goes live.

Open `index.html` in your browser and check the page at both **desktop width** and **phone width (375 px)**. In Chrome or Edge, press `Ctrl + Shift + M` to switch on the device toolbar.

## Your tasks

### 1. Fix what's broken
There are more than twenty problems hidden in `index.html` and `styles.css`. They cover layout, colours, links, forms, responsiveness and accessibility. Some are obvious at first glance; others only show up when you scroll, click, hover, press Tab, resize the window or read the code. Fixing one problem can reveal another.

### 2. Build the missing "Plans" section
It belongs between the Features section and the Contact section. The nav and hero buttons already link to `#plans`.

- Heading: **Pick your plan**, with the line "No contracts. Cancel or pause whenever you like."
- Three plan cards:

| Plan | Price | Tagline | Features |
|------|-------|---------|----------|
| Starter | $12 / month | For the occasional cup. | 1 bag (250 g) per month; choose any single-origin; free shipping over $10 |
| **Daily** (featured) | $24 / month | For a proper morning ritual. | 2 bags (500 g) per month; mix any two blends; free shipping; skip a month anytime |
| Office | $59 / month | For the whole team. | 6 bags (1.5 kg) per month; grind set for your machine; free shipping; priority support |

- The Daily card must stand out: a highlighted border and a **"Most popular"** badge.
- Each card has a "Choose ..." button that links to `#contact`.
- Cards are the same height, with the buttons lined up at the bottom.
- Three columns on desktop, one column on phones.
- It must look like it belongs: reuse the colours and fonts from the top of `styles.css`.

## Rules
- HTML and CSS only. No frameworks and no JavaScript.
- Keep the file and folder structure as it is. Do not rewrite the whole page from scratch.
- Test in your browser before you submit.
- Submit the whole `student` folder as a zip file.

**Deadline:** ______________________
