---
name: not-the-product
description: Check a feature of a community, forum, group or social app against one rule, "the members are never the product", and write plain promise text for members, each promise backed by a test or guard. Use when designing, building or reviewing feeds, notifications, groups, sign-up, email digests, newsletters, analytics, data export or deletion, moderation, or AI and search-engine access in such an app, or when the user asks for a member charter or asks whether a feature exploits users. Not for apps without a member community.
---

# Not the product

People become the product when the money comes from someone other than them. Ads pay for attention, so everything bends toward attention: a ranked feed, alarm-bell notifications, as much data as possible, hard to leave. This skill keeps a community app on the other side of that line, and makes the promises survive the day someone wants to bend them.

## Step 0: the project's own rules, and the off switch

Look first for the project's own charter or rules: a path named in `CLAUDE.md`, then `docs/**/CHARTER*.md`, then `.claude/not-the-product.md`.

- **If the project has a charter, it wins.** Check the feature against it, word for word. Use this file only for what the charter doesn't cover.
- **If `CLAUDE.md` or that file says `not-the-product: off`, stop** and say so in one line. That is the project's off switch.
- The skill only reads. It never edits a charter or code unless the user asks.

## Step 1: review the feature, layer by layer

Go through the layers the feature touches. For each, say what it does now (read the code, don't guess), whether it passes, and what to change. Skip layers it doesn't touch.

| Layer | Sells members out | Keeps them safe |
|---|---|---|
| **Money** | Ads, selling or sharing data, "engagement" as the business goal | Someone pays openly (the members, a club, the site owner). Write down who. |
| **Feed** | Ranking by reactions, time spent or outrage | Newest first, plus a few posts pinned by moderators. Any other order is explained to the reader. |
| **Notifications** | Messages from outside to pull people back: "you have 3 unread", "12 new posts", "you haven't been here in a week", "Anna and 5 others are active" | Only things addressed to the member: a reply, a mention, a decision about them. On-site counts are fine; the member is already there. |
| **Digest email** | On by default, more often when "a lot happens", counts of other people's activity, sent even when empty | Opt-in, off by default. At most weekly. Real content. Nothing sent when nothing happened. One-click stop with no login. No tracking pixels, no rewritten links. |
| **Data** | Third-party scripts, cookies that follow a person, profiles | No third-party trackers. Counting without cookies, with identifiers that don't survive the day. Photo location and camera metadata stripped on upload. |
| **Forgetting** | Keeping everything forever | Deleted content gone after a fixed, stated time. Account deletion anonymises posts, so others' conversations keep their shape. |
| **Power** | Silent removals and bans | A reason for every decision, an appeal, a log moderators can see, an undo window. |
| **Leaving** | Lock-in | A member downloads everything they wrote. A whole community can leave with its content, in an open format. |
| **AI and search** | Selling or opening content for AI training | Search engines and live AI fetchers that answer a question and link back may read public content. Training crawlers are refused. All AI companies get the same answer. Closed groups and members-only posts are never indexable and never served signed out. |
| **Consent** | One person deciding for others | Nobody consents for someone else. A group creator can't opt members into AI training. A post can't be made public after others replied to it for the group only; making something more private is always allowed. |
| **Shop and marketing** | Joining a group puts you on a list; posts used to target offers; the member list handed to a shop | Joining never adds anyone to a mailing list. Community content never chooses what anyone is offered. The site's own news and offers are a separate opt-in, never sold or shared. |
| **Changes** | New terms applied to everything already written | Changes announced before they happen. What was written before keeps the promises it was written under. |

Watch for the quiet versions: a count in a live-update endpoint that includes posts a signed-out reader can't open, a ban that doesn't reach a members-only area, a "share with partners" box ticked in advance, two opt-ins bundled into one ("to get the digest, accept marketing").

## Step 2: give every promise a guard

A promise without a guard is a hope. For each promise the feature makes or relies on, name what keeps it true when someone changes the code a year from now:

- a **test** (for example: a closed group's page, read signed out, is a 404 and carries `noindex`);
- a **lint or repo check** (for example: no script from a third-party origin, no new notification type without review, the marketing code never reads community tables);
- or **"to build"**, said plainly.

Put them in a table: promise, guard, status. Prove a new test is real: break the rule on purpose and check that the test fails.

## Step 3: write the promise text

Members read the promises, so they need the care a contract gets, in plain words. Method and examples: `references/writing-promises.md`. In short:

- **Benefits first.** Say what the member gains before the reservations. A text that opens with risks drives people away even when every word is true; the order is part of the honesty.
- **Reservations stay, behind a "Read more".** Layering isn't hiding when the main message is true on its own.
- **Nothing you can't keep.** "Usually link back", not "link back". "Disappears from here", not "disappears". "We say no", with the read-more saying it's a request.
- **Short sentences, everyday words.** No legal terms, no "we may".
- **A "why these words" note** for every choice, kept next to the text for whoever edits it later.
- **Test the text on a reader.** If the person who asked for it misreads a line, members will too. Rewrite it.

The person responsible for the app approves the final wording. Offer drafts and reasons; never settle the text alone.

## Step 4: report

One message:

1. The layers checked, pass or change, each in a line, with file and line where it matters.
2. The guard table.
3. Draft promise text, if asked for, with its "why these words".
4. The decisions that are the owner's, each with a recommended answer.

## What this skill never does

- Publish, deploy or post anything.
- Change a charter, privacy text or code without being asked.
- Treat a legal review as done. It checks design and wording against members' interests; privacy law is still a lawyer's job.
