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
- Which one or two tags?
- Can it go out now, or does it wait for a deploy or a fix? (Anything security-related that is still open waits. See redaction.)

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

1. **Intro, right under the title.** Two to four sentences for a reader who has never seen the project: what this is about, and why it matters to them. Label the parts in bold (**What this is about.** … **Why.** …).
2. **The story,** in sections, as it actually happened: the real error message, the real line of code, the real number.
3. **Outro, the last section: what happened, how it was solved, and how else it could be done.** One line per problem, one line per fix. Then the alternatives, honestly: what each would be better at and what it would cost. A small table works when there are several.
4. **A closing line** a reader can use: a checklist, a rule of thumb, or a link to the thing being built.

**Length:** 800 to 1200 words unless the rules say otherwise. Cut before you pad.

**Pictures: words where they travel, none on the page.**

- **Preview and social pictures carry the title.** Link previews, square and 4:3 feed images travel without the post, so the picture has to say what it is. Make one per shape the project's platforms crop to (often 1.91:1, 4:3 and 1:1).
- **The hero on the post page has no words.** The page already shows the title over or under it, so text in the picture only says it twice and fights the real title.
- If the project's rules name an image script or sizes, use those.

## Voice

Details and examples: `references/voice.md`. In short:

- **First person, the owner's voice.** It's their blog. Claude is "my AI" or "the AI", a character in the story, quoted only when it said something worth quoting.
- **Quote the owner's own words from the session** as the interview. Keep typos when they are part of the charm.
- **Dry humour, no hype.** Honest about what went wrong, including what the AI got wrong.
- **No em-dashes.** Use a new sentence or a comma.
- **Use they/them** for anyone whose pronouns aren't known.

## Step 3: redact. Every draft, every time

Run the full checklist in `references/redaction.md` before showing the draft as finished. It is not optional, and the project's own rules can add to it but never loosen it. The short version: no credentials (not even their shape), no hosts, IPs, ports, server paths, container or database names, no other people's names, no customer data, and **no security work that is still open**.

Anything undecided goes in an `<!-- HTML comment -->` for the owner.

## Step 4: hand over. Never publish

- Tell the user the full absolute path of the draft and what to check (intro, outro, redaction).
- **Upload only if the project rules name an upload command, and only after the user says yes.** Prefer an account that can only save drafts.
- **Never overwrite a draft that's already in the CMS** without asking: the owner may have edited it there.
- **Never post to social media** on your own. Prepare text if asked. The owner presses the button, one post at a time.

## What this skill does not do

- It does not trigger itself (`disable-model-invocation: true`). It runs only when the user calls it, so it never doubles up with an end-of-work question the project's `CLAUDE.md` already asks.
- It holds no credentials, hosts or project names. Everything project-specific lives in the project's rules file.
