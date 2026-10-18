# Ironpost

Responsive website for **Ironpost**, an imaginary SaaS company that offers secure, end-to-end encrypted file transfer for teams.
Built as the CSS group assignment: *Responsive Client Website with AI-Assisted Development*.

**Live site:** `https://lunamaldonado.github.io/practicum-program/`

## Team

| Name | GitHub | Main contributions |
|---|---|---|
| Luna | @lunamaldonado | landing page, pricing page, contact page, HTML + CSS |
| Ulugbek | @username | responsive layout, testing, README |
| Tehj | @t3hj |  landing page, feature page, burger menu |

## Pages

| Page | File | Purpose |
|---|---|---|
| Home | `index.html` | Landing page, follows the client's design |
| Features | `features.html` | Detail of each product feature |
| Pricing | `pricing.html` | Plans, comparison table, FAQ |
| Contact | `contact.html` | Contact options and form |

## Project structure

```
index.html
features.html
pricing.html
contact.html
css/
  style.css        shared stylesheet
images/
  hero-large.svg   hero illustration (tablet and desktop)
  hero-small.svg   simplified hero illustration (mobile)
```

## Technical requirements checklist

- [x] Semantic HTML (`header`, `nav`, `main`, `section`, `article`, `aside`, `figure`, `footer`)
- [x] Vanilla CSS in an external stylesheet (`css/style.css`)
- [x] Flexbox for the main layouts (no CSS Grid)
- [x] No JavaScript
- [x] Media queries at 768px (tablet) and 480px (mobile)
- [x] Responsive images
- [x] Roboto font, imported at the top of the stylesheet
- [x] Shared navigation and footer on every page
- [x] CSS-only burger menu on small screens
- [x] Font Awesome used only for icons
- [x] Collaborative GitHub repository

## Client design and typography

| Element | Style |
|---|---|
| Dark background (hero, footer) | `#1F2937` |
| Hero title | 48px, extra-bold, `#F9FAF8` |
| Hero subtext and header links | 18px, `#E5E7EB` |
| Header logo | 24px, `#F9FAF8` |
| Buttons and call-to-action background | `#3882F6` |
| Information section title | 36px, extra-bold, `#1F2937` |
| Quote section background | `#E5E7EB` |
| Quote text | 36px, light, italic, `#1F2937` |

## How the main techniques work

### CSS-only burger menu

A hidden checkbox (`#menu-toggle`) stores whether the menu is open. A `<label>` linked to the checkbox acts as the burger icon. On screens up to 768px the links are hidden with `display: none`, and the selector `.menu-toggle:checked ~ .nav` shows them when the checkbox is checked. The checkbox must come before the `nav` in the HTML so the `~` sibling selector can reach it.

### Responsive images

The hero image uses `<picture>` with a `<source media="(max-width: 480px)">`. This is **art direction**: phones receive a simplified illustration that stays readable at 375px, while larger screens receive the full scene. Both are SVG, so they stay sharp on any screen density and are very light. All images use `max-width: 100%` and `height: auto`, so they never overflow their containers or get distorted.

### Responsive layout

- Header, hero, cards, plans and contact layouts are Flexbox containers.
- On tablet the hero stacks vertically and the four cards wrap into 2 x 2.
- On mobile everything is a single column and the navigation becomes the burger menu.
- The pricing comparison table turns into stacked cards on tablet and mobile, so there is no horizontal scrolling.
- No content is removed on small screens; it is reorganised.

## Testing

Tested in browser DevTools at these widths:

| Width | Device | Result |
|---|---|---|
| 375px | Mobile | Corrected padding and adaptative layout |
| 768px | Tablet | Corrected padding and adaptative layout |
| 1200px+ | Desktop |  Corrected padding |

Checked: no horizontal scroll, readable text, images fit their containers, sections do not overlap, all pages usable.
HTML validated with <https://validator.w3.org/> : Document checking completed. No errors or warnings to show.

## AI usage log

Process followed: **Think → Try → Ask AI → Understand → Test → Accept, Modify or Reject**.

| # | Stage | What we thought or tried first | What we asked the AI | What it answered (summary) | Decision (accept / modify / reject) and why |
|---|---|---|---|---|---|
| 1 | Idea review after team meeting | SaaS Company in cibersecurity would match the design | Review and expand our idea | AI suggested names | We didnt like them and asked it to suggest more with futher indications | We chose one |
| 2 | Main site | Asked AI to suggest a website structure and content | Corrected and specified what we wanted | Asked AI to create an HTML/CSS site with the specifications | Asked AI to correct content, structure and style to our needs and judgment | Multiple iterations with AI to modify the website to the finished product
| 3 | Images | Asked AI to create images for the pages | It only placed icons so we asked for more detailed illustrations to give context to the product | AI created illustrations | Iterated on what should appear on the images, a slogan text for context | We checked the adjustments and asked for corrected paddings
| 4 | Final review of our work | Asked AI to self-check the work based on given specifications | Reviewed the page and detected errors (paddings, adaptability, horizontal scroll...) | Iterated with AI to fix mistakes | Final check before publishing |

## Known limitations

- Header and footer are repeated in each HTML file, because includes would need JavaScript or a server.
- The contact form has no back end (`action="#"`).
- The CSS-only burger menu cannot update `aria-expanded` without JavaScript.
- The client's blue (`#3882F6`) with white text has a contrast of about 3.5:1, below the 4.5:1 recommended for small text.
- All company content (names, prices, quotes, e-mail addresses) is fictional.

## How to run

No build step. Open `index.html` in a browser, or enable GitHub Pages (Settings, Pages, deploy from branch `main`, folder `/ (root)`).
