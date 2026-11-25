# Design slop: patterns, what to do instead, and the checks

Design slop is a page that could belong to any product. It usually comes from starting with a layout and filling it, instead of starting with what this visitor came to do and what only this project can show them.

Look at the page running, at more than one width, before reading its code. The code tells you what was intended. The page tells you what happens.

## 1. The template page

**Looks like:** a gradient hero with a big vague promise, three feature cards (icon, two-word title, two-line claim), a logo row, a testimonial carousel, a rounded call-to-action, a four-column footer. Swap the logo and it's someone else's site.

**Instead:** start from what only this project has: the product in use, a real screenshot, real numbers, the real people, the one thing the visitor came to do. Replace each card's claim with the evidence for it, or cut the card. The section order follows the visitor's questions, not the template's.

> **Slop:** three cards: "⚡ Fast", "🔒 Secure", "🤝 Collaborative".
> **Better:** one screenshot of the editor with two cursors in it, captioned "Two people editing the same paragraph, no conflicts". Below it, the one security fact a buyer asks about, linked to the page that proves it.

## 2. Decoration without a job

**Looks like:** gradient blobs, glass panels, floating 3D shapes, abstract illustrations of people at laptops, generated art that matches nothing else on the site, emoji as icons, animations on scroll for every block, a badge that says "New" for a year.

**Instead:** give each visual element a job: show the product, explain a step, guide the eye to the main action, or carry the brand where it matters (a header, one hero). If it does none of those, remove it. A real photo of the product, the place or the people beats an illustration of the idea of them.

## 3. Proof that isn't proof

**Looks like:** logos of companies with no case behind them, testimonials with only a first name and a stock photo, "Trusted by thousands", star ratings with no count or source, counters that only go up.

**Instead:** show proof a visitor could check: a named customer with a link to their story, a real count with a date ("1,240 shops, March 2026"), a quote with a full name and role, given with permission. If you don't have proof yet, leave the section out. Never invent testimonials, reviews, logos or numbers.

## 4. Everything loud, so nothing scans

**Looks like:** every button the same heavy weight, every heading the same size, colour on everything, several elements competing to be first. The eye has nowhere to start.

**Instead:** one main action per view at full weight, the rest quieter (smaller, outlined, plain text). Size and weight follow importance, and colour guides instead of decorating. Keep hit areas big even when the visual gets small (44 px on touch).

## 5. A style that doesn't fit the content

**Looks like:** a playful style on a page about money or illness, a dense dashboard skin on a page with one action, a style so strong that the content (the members' posts, the product photo, the article) is the quietest thing on screen.

**Instead:** decide what the visitor must notice first, and make the style serve that. Let it be loud where it carries the brand and quiet where the content lives.

## 6. Buttons and links that say nothing

**Looks like:** "Learn more", "Get started", "Click here", "Submit", "Discover", repeated on every card, each one going somewhere different.

**Instead:** say what happens: "See pricing", "Book a table for tonight", "Download the PDF (2 MB)". A link's text should make sense read alone, which also helps screen reader users who list the links on a page.

## 7. Visual inconsistency

**Looks like:** spacing that changes from section to section, icons from two sets, corner radii that differ between cards and buttons, near-identical colours that aren't the same token, three font sizes that are almost the same.

**Instead:** use the project's own tokens and components, or name the one value it should be. If the project has no design system, the finding is the list of values that should become one.

## 8. Only the happy path was designed

**Looks like:** the page works with the mockup's perfect content: short names, three items, a fast connection. Nobody designed the long title, the empty list, the error, the slow load or the visitor who isn't signed in.

**Instead:** design each state with words a visitor can act on. An empty state says how to fill it. An error says what happened and what to do next, using the server's real message where it helps. Loading keeps the layout still.

## 9. Pressure in place of reasons

**Looks like:** countdown timers that reset, "Only 2 left!" on everything, pop-ups before the page has loaded, a cancel link in grey on grey, a pre-ticked newsletter box.

**Instead:** give the visitor reasons, and let them decide. Real scarcity can be stated plainly ("Ships after 12 January, last batch this year"). Leaving or saying no is as easy to find as saying yes.

## The checks

Run these, and report the ones you didn't:

- **Phone width** (about 360 px) and a wide desktop. Nothing overflows sideways, and nothing important is pushed below a decoration.
- **Keyboard only.** Tab through everything. Each control can be reached, its focus is visible, and the order makes sense. Menus and dialogs close with Escape and give focus back.
- **Contrast.** Body text at least 4.5:1, large text and control edges 3:1. Colour is never the only cue.
- **Zoom to 200%.** Text reflows, and nothing is cut off or overlaps.
- **Long content.** The longest real name, title or translation (German words are long), a number with many digits.
- **Empty content.** A new account, an empty list, no image.
- **Slow and failing.** A slow connection, a failed request, no permission, signed out.

## A design finding names who, what and the evidence

Say **who it helps** (which visitor), **what task it improves** (find, compare, buy, post, leave), and **the evidence**: a screenshot at the width where it breaks, a contrast ratio, a Tab order, a real content example. "It feels busy" is a start. "On a phone, the post's text is the fourth thing you see, after three framed buttons" is a finding.
