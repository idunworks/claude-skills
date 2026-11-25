---
name: non-slop
description: A library of slop patterns (generic words, stock phrases, same-shaped sentences, borrowed authority, empty wisdom, encyclopedia filler, missing substance, template web design) with what to write or design instead, and slop-to-better pairs for common genres. Use when writing or reviewing text or pages meant for readers (blog posts, landing pages, product copy, outreach and marketing emails, cover letters, support replies, social posts, error and empty-state messages), or when the user types /non-slop or asks whether something reads generic. Not for code, commit messages, chat replies to the user, messages to other agents, or internal notes.
---

# Non-slop

Slop is work that could have come from anywhere. The sentence opens anyone's post; the hero sits on anyone's product; the advice fits every reader and helps none. It isn't always wrong. It's swappable, and readers notice that within a line.

This skill is a library and two ways to use it: **write** it right the first time, or **review** what's already written. It judges the work, never who or what made it. Plenty of slop is written by people, and plenty of good text by machines.

## Step 0: the project's own rules, and the off switch

- **If `CLAUDE.md` says `non-slop: off`, stop** and say so in one line.
- **Read the project's own style rules first:** a voice or style section in `CLAUDE.md`, a brand guide, a design system. They win. A fragment the house style asks for is voice, not slop. A word on the list that the author chose on purpose stays.
- **Never invent the substance.** The cure for slop is a real fact, number, name, constraint or example. If you don't have it, ask for it or leave a marked gap (`[how long did setup take?]`). A made-up specific is worse than a vague line, because it reads as true.

## The library

| File | What's in it |
|---|---|
| `references/patterns.md` | The ten kinds of text slop: what each looks like, why it reads as slop, and what to write instead, plus the read-aloud test |
| `references/words.md` | Words and phrases that read generic, grouped, with plain swaps, and why swapping words alone fixes nothing |
| `references/genres.md` | Slop and better versions side by side: landing page, error message, release note, product page, support reply, blog intro, social post, outreach email, job application, customer review, closing paragraph |
| `references/design.md` | Design slop: template pages, everything loud, decoration without a job, missing states, controls that do nothing, and the checks to run |

Read the one that fits the task. For a landing page, that's `genres.md` and `design.md`. For a cover letter, `genres.md` and `patterns.md`.

## Mode 1: write it right the first time

Before the first sentence, answer these four questions in your head, or out loud if you're missing answers:

1. **Who reads it, and what should they know or do afterwards?** One reader, one outcome.
2. **What do I actually have?** List the facts, numbers, names, quotes, dates, screenshots, the thing that went wrong. This is the material. Everything else is framing.
3. **What's the one point?** If it takes more than a sentence, there are two pieces.
4. **What would only this author, product or project say?** That's where the piece starts.

While writing:

- **Start with the material, not the frame.** The first line is a fact, a moment, a number or the reader's problem, not the state of the world.
- **Say each thing once,** where it's earned. No intro that previews and no outro that repeats.
- **Every claim gets a source, a measurement, or an "I think".** Every specific you keep (a number, a date, a quote, a feature) is one you checked. A precise number nobody looked up is worse than none.
- **Let the shape follow the content.** Use a list where things are parallel, a story where they're not. Vary sentence and paragraph length because the thoughts differ, not as a trick.
- **Plain words.** "Use", not "leverage". The word list is in `references/words.md`.
- **End on the last real point,** a trade-off, or what's still open. Not a moral.

Then read it aloud once, and run the review pass below on your own draft before handing it over. Mention in a line what you changed or couldn't fix ("the cost line needs a real number").

## Mode 2: review

Read the work once, whole, as its reader would. For a page that's already running, open it at phone and desktop width and use it with the keyboard before reading the code. Then ask five questions:

1. **What is it for?** One reader, one outcome.
2. **Which claims can be checked, and do they hold?** Look the specifics up (`patterns.md` 6 and 10).
3. **Could it be swapped into an unrelated product unchanged?** Every line that could is a finding.
4. **What's missing?** Constraints, exceptions, examples, the cost; for pages, the empty, long, error and keyboard states.
5. **What would you cut or rewrite first?**

Then go through `references/patterns.md` (and `design.md` for pages) and report, in one message:

1. **What it's for,** in a sentence, as you read it. If that differs from what the author meant, say so. That alone is useful.
2. **Findings,** most important first, at most about seven. Each one has:
   - **where:** a quote of a few words, a heading, a component, a screen width;
   - **which pattern:** a name from the library, and why it fits here;
   - **a concrete change:** the rewritten line, the cut, the fact to add, the state to design. Never just "make it more specific";
   - **one honest question,** when the fix needs something only the author knows ("What did it actually cost?").
3. **What already works,** in a line or two, so it survives the next edit.
4. **What you didn't check:** not run, not seen on a phone, no screen reader.

A clue isn't a finding until you can point to the place and say what would be better. One "crucial" in a long piece is just a word. The tell is density: the same move, again and again.

## What this skill never does

- **Help text pass as human, or get past an AI detector.** It isn't about hiding where text came from. It's about text that's worth reading. If that's the request, say so and offer the quality pass instead.
- **Label work "AI-written", or score it as such.** It names a pattern, a place and a change.
- **Invent facts, quotes, numbers, people, reviews or results** to make text sound specific.
- **Flatten a voice.** Fragments, profanity, odd jokes and strong opinions are specific, not sloppy.
- **Publish, post or deploy anything,** or rewrite the work unless asked.

## Further reading

Two pages that sorted slop into kinds before this one did, worth reading in full:

- [SlopDetector](https://slopdetector.org/) scores text on vocabulary, clichés, structure, diversity and substance, and keeps a [list of overused words](https://slopdetector.org/blog/ai-words-list). It judges quality, not origin.
- [StealthGPT's "AI slop examples"](https://www.stealthgpt.ai/blog/ai-slop-examples) collects real-world cases and before-and-after pairs for everyday genres. That company sells a tool for getting past AI detectors. This skill doesn't share that goal, but the examples are a good read.

Patterns 1 to 5 in `patterns.md` follow SlopDetector's five dimensions, and the genre-pair format in `genres.md` follows StealthGPT's examples. The pairs and wording in this library are our own. Lists like these go stale as habits change, so check the current versions of both.
