---
name: not-generic
description: Review a finished piece of work, a text (blog post, docs page, announcement, product copy) or a web page or component, for generic, unsupported, repetitive or unconsidered work, and name a concrete change for each finding. Runs only when the user types /not-generic, for example to find out whether a draft reads generic or a page looks like a template.
disable-model-invocation: true
---

# Not generic

Generic work isn't wrong. It's swappable: the same sentence could open anyone's post, and the same hero could sit on anyone's product. This skill reads finished work the way a sharp editor or a tired visitor would, and asks what in it could only have come from this project.

The goal is never to label work "AI". Plenty of generic text was written by people, and plenty of good text by machines. The point is to catch work that is generic, unsupported, repetitive or unconsidered, whoever made it, and to say what would make it specific.

## Step 0: the project's own rules, and the off switch

- **If `CLAUDE.md` says `not-generic: off`, stop** and say so in one line.
- **Read the project's own style rules first**: a voice or style section named in `CLAUDE.md`, a design system, a brand guide. They win. A short sentence the house style asks for isn't a finding; a rounded button the design system forbids is.
- The skill only reads and reports. It edits nothing unless the user asks for the rewrite.

## Step 1: read it the way it will be met

- **Text:** read it whole, once, as the reader it's for. Then read it aloud, or as close as you can: rhythm problems are heard before they are seen.
- **A page or component:** open it running, if you can, not only its code. Look at it at phone width and desktop width, then use it with the keyboard alone. Clues and checks: `references/web-design.md`.
- Note what you see first and what you have to hunt for. That order is the design, whatever the intent was.

## Step 2: the five questions

Answer each one in a line or two, about this work:

1. **What is it for?** Who is it for, and what should they know or be able to do after it? If you can't say, that is the first finding.
2. **What can be checked?** Point to the facts, numbers, names, quotes and claims. Which have a source, a test, a link or a firsthand observation behind them, and which are confident and unchecked?
3. **Could it be swapped into an unrelated product unchanged?** Point to the sentences, sections or blocks that could. Those are the generic parts.
4. **What's missing?** The real world: constraints, trade-offs, what went wrong, the exception, the number, the person. For a page: the states (long, empty, error, loading, no results), the keyboard path, the small screen.
5. **What would you cut or rewrite?** Name the lines and the blocks.

The clue lists are in `references/text.md` and `references/web-design.md`. Use them to look harder, not as a score: a finding needs a place in the work, not just a clue that matches.

## Step 3: report

One message, in this order:

1. **What it's for,** in a sentence, as you read it. If that differs from what the author meant, say so: that alone is useful.
2. **Findings,** most important first, at most about seven. For each:
   - **where** (a quote of a few words, a heading, a component, a screen width);
   - **what's generic or unsupported about it**, in a line;
   - **a concrete change**: the rewritten sentence, the fact to add, the block to cut, the state to design. Not "make it more specific";
   - **one honest open question** when the fix needs something only the author knows ("What did it actually cost?", "Which reader is this card for?"). Never invent the answer: no made-up numbers, quotes, people or test results.
3. **What already works,** in a line or two, so it survives the next edit.
4. **What you didn't check** (not run, not seen on a phone, no screen reader), plainly.

Real before-and-after examples of each kind: `references/examples.md`.

## What this skill never does

- Trigger itself. It runs only when the user calls it.
- Rewrite the work unasked, or publish, post or deploy anything.
- Call something "AI-written", or score it as such. It names a place and a change.
- Add facts, quotes, numbers or anecdotes that aren't in the author's material. A missing fact becomes a question.
- Flatten a voice. Fragments, profanity, odd jokes and strong opinions that the author chose are specific, not sloppy. If the project has a voice guide, they are probably in it.
