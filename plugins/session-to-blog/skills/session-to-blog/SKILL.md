---
name: session-to-blog
description: Turn a finished piece of work from this Claude session into a first-person blog post draft in the project owner's voice, with an intro, an outro that weighs alternatives, and a redaction pass. Use when the user types /session-to-blog, or asks to "blog this", "write this up as a post" or "draft a post from this session".
disable-model-invocation: true
---

# Session to blog

The session is the interview. The project's blog folder is the notebook. The CMS (or wherever posts live) is where it goes live, and only the owner puts it there.

## Step 0: find the project's own rules, and obey them first

Before anything else, look for the project's blog rules, in this order:

1. A path named in `CLAUDE.md` (for example "follow `docs/blog/README.md`")
2. `docs/blog/README.md`
3. `.claude/blog-rules.md`

**If a rules file exists, it wins** over everything below: folder, file name, frontmatter, tag list, voice reference, upload command. This skill only fills the gaps it leaves.

**If the rules or `CLAUDE.md` say blog drafts are off, or put this topic on hold, stop** and tell the user in one line. That is the project's off switch.

If there are no rules, use the defaults in this file and offer once, at the end, to save them as `docs/blog/README.md` (template: `references/project-rules-template.md`).

## Step 1: the follow-up questions

Calling `/session-to-blog` is the yes, so don't ask whether it's blog material. If the work looks routine, say so in one line and offer to stop. Good material is a story, a mistake worth sharing, a technique, a "you won't believe what was wrong".

Ask the follow-ups in **one** message, each with a recommended answer, **before writing the draft**. If the user already answered some, skip those. In a non-interactive run, use the recommended answers and list them at the end:

- Social media, and which platforms?
- A cross-post (dev.to or similar)?
- Pictures: a preview image with the title on it, and a hero picture without words?
- Part of a series?
- Which one or two tags? A tag that every post would carry (the tool you always use, the way you always work) filters nothing: leave it out.
- Can it go out now, or does it wait for a deploy or a fix? (Anything security-related that is still open waits. See redaction.)

**The title is the owner's.** Offer two to four options and let them pick or write their own. Never settle it alone. A good title:

- is short, about 4 to 8 words, well under 60 characters, so search results show all of it;
- names what a reader would search for, with the payoff in it ("Stop your save button from forgetting"), not a clever "My X did Y" twist;
- never starts with "My", and isn't a long sentence with a comma and a second clause.

## Step 2: write the draft

**Default file:** `docs/blog/YYYY-MM-DD-<slug>.blog.md`. The date is today, the slug is the post's future URL.

**Default frontmatter:**

```markdown
---
title: "The headline"
date: YYYY-MM-DD
tags: [one, two]
excerpt: "One or two sentences for listings and search results."
status: draft
source: "which session or feature this came from"
---
```

**Structure. Every post has all four parts:**

1. **Intro, right under the title.** What this is about and why it matters, for a reader who has never seen the project. Best when it starts in the middle of something (a day, a broken page, a sentence the owner said) and lets that scene carry the what and why. Bold labels (**What this is about.** … **Why.** …) are optional: they help a long technical post be skimmed, but on every post they read like a report.
2. **The story,** in sections, as it actually happened: the real error message, the real number. Code only where there is a real lesson in it (a few lines a reader could copy, or the one line that was the bug). Many posts should have none: a story that works in plain words stays in plain words.
3. **Outro, the last section: what happened, how it was solved, and how else it could be done.** One line per problem, one line per fix. Then the alternatives, honestly: what each would be better at and what it would cost. A short paragraph or a list is usually enough; a table only when several options compare on the same points.
4. **A closing line** a reader can use: a rule of thumb, a two-minute test, or a link to the thing being built.

**Length:** aim for 800 to 1000 words, and cut hard past about 1150. Shorter is better. Cut what only the project's own people care about before you trim anything else.

**Pictures: words where they travel, none on the page.**

- **Preview and social pictures carry the title.** Link previews, square and 4:3 feed images travel without the post, so the picture has to say what it is. Make one per shape the project's platforms crop to (often 1.91:1, 4:3 and 1:1).
- **The hero on the post page has no words.** The page already shows the title over or under it, so text in the picture only says it twice and fights the real title. A screenshot of the real thing makes a good hero.
- **Make the pictures before the first upload.** Once the owner schedules or publishes a post, a drafts-only account may not be able to change it without sending it back to draft, and a link shared without its picture stays that way in platforms' caches for days.
- If the project's rules name an image script or sizes, use those.

## Voice

Details and examples: `references/voice.md`. In short:

- **First person, the owner's voice.** It's their blog, written for visitors, not for the project's own people.
- **The owner and the AI are "we".** No "I asked my AI": it isn't a story, and readers don't care who typed. Mention the AI only where it is the point.
- **The technology is the character.** The save button that forgets, the layout that argues with itself, the deploy that sulks. The drama is between people and machines.
- **The owner decides; they don't plead.** "I wanted…", "To do X, I needed Y". Never "I asked for", "I wished", "please".
- **Quote the owner's own words sparingly,** cleaned up (typos fixed) and phrased as what they needed. A quote that reads better as story goes into the prose instead.
- **Leave room for the owner.** Where their aside, opinion or history belongs, put an `<!-- your aside: … -->` comment. Don't invent biography, and don't fake their English with planted typos.
- **Dry humour, uneven rhythm, no hype.** Honest about what went wrong, including what the AI got wrong.
- **No em-dashes.** Use a new sentence or a comma. **They/them** for anyone whose pronouns aren't known.

## Step 3: redact. Every draft, every time

Run the full checklist in `references/redaction.md` before showing the draft as finished. It is not optional, and the project's own rules can add to it but never loosen it. The short version: no credentials (not even their shape), no hosts, IPs, ports, server paths, container or database names, no other people's names, no customer data, **no security work that is still open anywhere**, and no description of how the system is wired together. Then the mosaic check: what does this post add to what earlier posts already told?

Anything undecided goes in an `<!-- HTML comment -->` for the owner.

## Step 4: hand over. Never publish

- Tell the user the full absolute path of the draft and what to check (title, intro, outro, redaction).
- **Upload only if the project rules name an upload command, and only after the user says yes.** Prefer an account that can only save drafts.
- **Never overwrite a draft that's already in the CMS** without asking: the owner may have edited it there.
- **After the owner publishes, pull their edits back** into the repo file. The live post is the truth; the file follows it, never the other way. While you're there, check the preview image and the hero picture are set.
- **Never post to social media** on your own. Prepare text if asked. The owner presses the button, one post at a time.
  - **No domain names in social text** (like "monday.com"): several platforms turn them into links and build the preview card from the first one, so the card shows someone else's site. Write "the app Monday".
  - **Check the real link card** (title, description, picture) before anything is posted.

## What this skill does not do

- It does not trigger itself (`disable-model-invocation: true`). It runs only when the user calls it, so it never doubles up with an end-of-work question the project's `CLAUDE.md` already asks.
- It holds no credentials, hosts or project names. Everything project-specific lives in the project's rules file.
