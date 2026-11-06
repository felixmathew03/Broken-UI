# BrewLab Round 1: Organizer Answer Key

**Do not share this file with students.**

- `student/` is the broken page they receive.
- `organizer/solution/` is the working reference (all bugs fixed, Plans section built).
- `organizer/bugs.diff` is the exact diff between the two.

## A. Bugs to fix (25 bugs, 4 points each = 100 points)

### index.html

| # | What is broken | What students will see | Fix | Level |
|---|----------------|------------------------|-----|-------|
| H1 | Hero image `src="image/cup.svg"` (the folder is `images`) | Broken image icon in the hero | `images/cup.svg` | Easy |
| H2 | Hero `<img>` has no `alt` attribute | Nothing visible; fails an accessibility check | Add a descriptive `alt` | Easy |
| H3 | `<meta name="viewport">` missing from `<head>` | On a real phone the page renders at desktop width, zoomed out | Add `<meta name="viewport" content="width=device-width, initial-scale=1.0">` | Medium |
| H4 | Features heading is an `<h4>` and has lost its `section-title` class | Small, left-aligned heading; wrong heading level | `<h2 class="section-title">` | Easy |
| H5 | Nav link points to `#feature`, but the section id is `features` | Clicking "Features" does not scroll | `href="#features"` | Easy |
| H6 | `<label for="mail">` but the input id is `email` | Clicking the "Email" label does not focus the field | `for="email"` | Medium |
| H7 | Email field has `type="text"` | No email validation, no email keyboard on phones | `type="email"` | Medium |
| H8 | The second feature card is missing its closing `</article>` | The third card renders nested inside the second (a card within a card) and the grid has only two items | Add `</article>` after the second card's paragraph | Hard |
| H9 | Submit button has `type="button"` | Clicking "Send message" does nothing: no validation messages, no submit | `type="submit"` | Medium |
| H10 | `<html>` has no `lang` attribute | Nothing visible; screen readers may read the page in the wrong language | `<html lang="en">` | Easy |
| H11 | `<title>` is the placeholder "Document" | The browser tab says "Document" | A descriptive title, for example "BrewLab \| Small-batch coffee, delivered" | Easy |
| H12 | The message `<textarea>` has no `name` attribute | The message is missing from the submitted data (look at the URL query after submitting; needs H9 fixed first) | `name="message"` | Medium |

### styles.css

| # | What is broken | What students will see | Fix | Level |
|---|----------------|------------------------|-----|-------|
| C1 | Typo `dispaly: flex` in `.nav-links` | Nav links stacked vertically, header grows tall | `display: flex` | Easy |
| C2 | `.hero h1` colour `#3d2a20` on a `#2b1d16` background | Headline almost invisible | Light colour such as `#fff9ef` (any colour with 4.5:1 contrast or better) | Easy |
| C3 | `repeat(3 1fr)` is missing a comma | Invalid value, so the feature cards stack in one column | `repeat(3, 1fr)` | Medium |
| C4 | `box-sizing: border-box` removed from the `*` rule | Form fields (name, email, message) stick out about 30 px past the form card's padding | Restore `box-sizing: border-box` | Hard |
| C5 | `z-index: 10` removed from `.site-header` | When scrolling, the cards slide over the sticky header | Restore `z-index: 10` | Hard |
| C6 | `@media (max-width 720px)` is missing the colon | The whole mobile block is ignored: hero does not stack, cards stay in 3 columns | `(max-width: 720px)` | Medium |
| C7 | `.hero-img { width: 420px; }` | **Visible only after C6 is fixed:** at 375 px the image overflows and the page scrolls sideways | `width: 100%; max-width: 420px;` | Medium |
| C8 | Selector typo `.btn:hovr` | Buttons do not darken or lift on hover (the outline button still does) | `.btn:hover` | Medium |
| C9 | `.section-sub` colour `#d6cbbb` | The grey sub-headings under each section title are barely readable | `color: var(--muted)` (or any colour with 4.5:1 contrast) | Easy |
| C10 | Focus rule on the form fields is `outline: none` | No visible focus ring when tabbing into the fields | Restore an outline, or give a clear focus style | Medium |
| C11 | `gap: 24px` removed from `.cards` | The feature cards touch each other with no space between them (vertically while stacked, and sideways once C3 is fixed) | `gap: 24px` | Medium |
| C12 | `.hero h1` font size fixed at `4rem` | The headline is huge on phones (64 px) | `font-size: clamp(2.2rem, 5vw, 3.4rem)` | Medium |
| C13 | `.btn-outline` text colour is `var(--dark)` | The "How it works" button text is invisible (dark on dark) until hover | `color: var(--cream)` | Easy |

Totals: 10 easy, 12 medium, 3 hard = **25 bugs = 100 points**. If you want harder bugs to count more, weight them yourself (for example easy 3, medium 4, hard 8).

Notes for judging:
- Accept any valid fix that removes the symptom, not only the exact line above.
- Some bugs only appear after another is fixed: C7 after C6, and H12 after H9 (or by reading the code).
- H3 also affects the mobile checks. On a real phone, or in the browser's device-toolbar emulation, a page without the viewport meta tag lays out at desktop width, so the mobile layout (C6) never kicks in until H3 is fixed. In a plain narrowed desktop window it makes no difference.
- The submit button does not overflow in C4 because browsers give buttons border-box sizing by default. Only the text fields and the message box do.
- C4, C5, C10 and H8 are the "invisible until you test" bugs. Look for students who tabbed through the form, scrolled the page and inspected the HTML structure.
- To make the challenge easier, remove any bug by copying the matching line from `organizer/solution` into the student files, and adjust the points.

## B. Plans section build (suggested 50 points)

| Criteria | Pts |
|----------|-----|
| Correct structure: `id="plans"`, placed between Features and Contact, headings, lists, links to `#contact` | 15 |
| Visual match with the rest of the page (colours, fonts, spacing, reuse of existing classes or variables) | 15 |
| Responsive: 3 columns on desktop, 1 column at 375 px, no horizontal scroll | 10 |
| Polish: featured card with border and "Most popular" badge, equal card heights, buttons aligned at the bottom | 10 |

Watch for: a featured badge that slides over the sticky header when scrolling (a student who fixed C5 will already know why this does not happen).

## How to check a submission quickly
1. Open `index.html` at full width, then at 375 px in the browser's device toolbar.
2. Check the browser tab title, then click each nav link and the hero buttons (hover over them too).
3. Click each form label, try an invalid email, press Tab through the fields, and click "Send message".
4. Scroll slowly and watch the header.
5. Compare with `organizer/solution/index.html` if you are unsure what "correct" looks like.
