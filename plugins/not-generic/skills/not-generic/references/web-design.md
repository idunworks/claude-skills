# Web design: clues, fixes and the checks

Look at the page running, at more than one width, before reading its code. The code tells you what was intended; the page tells you what happens.

## Template sameness

**Looks like:** a gradient hero with a big vague promise, three feature cards with an icon and a two-line claim each, a row of logos, a rounded call-to-action. It could be any product's page.

**Fix:** start from the content only this project has: the real product in use, the real numbers, the real people, the thing the visitor came to do. Replace a card's claim with the evidence for it, or cut the card.

## A design that doesn't fit the content

**Looks like:** a playful style on a page about money or health; a dense dashboard skin on a page with one action; a style so strong that the content (the members' posts, the product photo, the article) is the quietest thing on screen.

**Fix:** decide what the visitor must notice first, and make the style serve that. The style is allowed to be loud where it carries the brand (a header, one card, the main action) and quiet where the content lives.

## Everything loud, so nothing scans

**Looks like:** every button the same heavy weight, every heading the same size, colour used on everything, so no element leads. The eye has nowhere to start.

**Fix:** one main action per view at full weight; the rest quieter (smaller, outlined, plain). Size and weight should follow importance, and colour should guide rather than decorate. Keep the hit area big even when the visual gets small (44 px on touch).

## Untested details

Check these, and report what you didn't:

- **Phone width** (about 360 px) and a wide desktop. Nothing overflows sideways; nothing important is pushed below a decoration.
- **Keyboard only:** Tab through everything. Each control can be reached, its focus is visible, and the order makes sense. Menus and dialogs close with Escape and give focus back.
- **Contrast:** body text at least 4.5:1, large text and control edges 3:1. Colour is never the only cue.
- **Zoom to 200%:** text reflows, nothing is cut off or overlaps.
- **Long content:** the longest real name, title or translation (German words are long), a number with many digits.
- **Empty content:** a new account, an empty list, no image.

## Visual inconsistency

**Looks like:** spacing that changes from section to section, icons from two different sets, corner radii that differ between cards and buttons, near-identical colours that aren't the same token.

**Fix:** use the project's own tokens and components, or name the one value it should be. If the project has no design system, the finding is the list of values that should become one.

## Elements that do nothing

**Looks like:** a link that goes nowhere useful, an icon that looks clickable but isn't, a carousel nobody needs, a badge or animation that carries no information, a "Learn more" that repeats the card.

**Fix:** remove it, or give it a job and a label that says what the job is.

## Missing real content states

**Check:** long names, errors (including the server's own message, not just "Something went wrong"), loading (and slow loading), no results for a search or filter, no permission, signed out.

**Fix:** design each state with words a visitor can act on: what happened, and what to do next. An empty state should say how to fill it.

## The fix: who, what, evidence

A design finding names **who it helps** (which visitor), **what task it improves** (find, compare, buy, post, leave), and **the evidence**: a screenshot at the width where it breaks, a contrast ratio, a Tab order, a real content example. "It feels busy" is a start; "on a phone, the post's text is the fourth thing you see, after three framed buttons" is a finding.
