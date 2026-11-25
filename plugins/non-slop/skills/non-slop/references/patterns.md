# The nine kinds of text slop

Each kind has what it looks like, why readers notice it, what to write instead, and a small pair. The pairs are invented to show the move. The facts in the "better" lines stand in for facts you have; never borrow them.

A pattern becomes a finding only when you can quote the place. The tell is density: one stock phrase is a habit, the same move in every paragraph is slop.

## 1. Inflated vocabulary

**Looks like:** big words for small actions ("leverage", "utilize", "facilitate", "embark on"), hype adjectives ("cutting-edge", "robust", "seamless", "powerful"), intensifiers piled up ("truly", "incredibly", "deeply").

**Why it reads as slop:** the word is bigger than the thing. A reader learns nothing from "robust" and starts skimming.

**Write instead:** the plain verb, and the fact that made the adjective true. If there's no fact, the adjective goes too.

> **Slop:** Our robust platform seamlessly empowers teams to leverage their data.
> **Better:** The import reads a 40 MB spreadsheet in about ten seconds, and keeps your column names.

The grouped list with swaps is in `words.md`.

## 2. Stock phrases

**Looks like:** openers and closers that fit any topic. "In today's fast-paced world", "Let's dive in", "When it comes to", "At the end of the day", "It's no secret that", "Game-changer", "Take it to the next level".

**Why it reads as slop:** the reader has seen the phrase a thousand times, so it signals that no one chose these words for this piece.

**Write instead:** cut it and read the next sentence. It usually starts the piece better on its own. If something is lost, say that thing directly.

> **Slop:** In today's ever-changing digital landscape, security has never been more important.
> **Better:** Last March, someone signed in to our admin page with a password from a 2019 leak.

## 3. Same-shaped structure

**Looks like:**

- every section is a claim, three bullets and a summary line;
- lists of exactly three, again and again;
- paragraphs of the same length;
- headings in matching grammar ("Understanding X", "Exploring Y", "Embracing Z");
- "It's not X, it's Y" as a reflex;
- a staged reveal in every paragraph ("The result?", "Here's the thing:");
- bold lead-ins on every bullet, even when the bullets are one line.

**Why it reads as slop:** the shape came first and the content was poured in. Readers feel the template before they can name it.

**Write instead:** let the content pick the shape. Two options make a list of two. A story makes paragraphs. One surprising result can be one short line. Keep bullets for things that really are parallel: steps, options, a checklist.

> **Slop:** It's not just a tool. It's a mindset. The result? Teams that move faster, think smarter and build better.
> **Better:** We used it for a month on one team. Their releases went from fortnightly to weekly. The other team didn't change, and we still don't know why.

## 4. Sameness

**Looks like:** the same point made in the intro, in each section and in the outro. The same few words over and over ("ensure", "key", "journey"). Every sentence opening the same way. Every paragraph ending on a neat line.

**Why it reads as slop:** the piece is longer than its content. The reader is told three times and shown once.

**Write instead:** say the point once, after the thing that proves it. Make each section add something new: an example, a cost, an exception, a counter-argument. If a section adds nothing, cut it.

> **Slop:** In conclusion, as we've seen, consistency is key. Being consistent is what ultimately drives results.
> **Better:** (Cut it. The post already showed this with the six-month chart. End on what's still open: whether it holds for a team of one.)

## 5. Missing substance

**Looks like:** nothing in the piece could have gone differently. No number, no date, no name, no constraint, no trade-off, nothing that took three tries, no "this didn't work". Advice with no case it came from.

**Why it reads as slop:** it's the clearest tell of all. Text with no particulars could have been written without doing the work.

**Write instead:** go back to the material. What broke first? What did it cost in time or money? Who noticed? Which case still fails? One true detail does more than a paragraph of framing. If you don't have it, ask the author. Never make it up.

> **Slop:** Migrating our database was challenging, but with careful planning we achieved a smooth transition.
> **Better:** The migration took two weekends instead of one: a column of dates stored as text in three formats. We wrote a parser for all three and kept the old column for a month.

## 6. Borrowed authority

**Looks like:** "studies show", "experts agree", "research suggests", "it's widely known", "many companies find", "according to industry leaders". A famous quote with no source. A statistic with no year or origin.

**Why it reads as slop:** it claims weight without showing it. Readers who check find nothing, and then doubt the rest.

**Write instead:** name the source and link it, give your own measurement with its setup, or say plainly that it's your view. A quote's attribution gets checked before it stays. If there's no source, the claim goes or becomes an opinion.

> **Slop:** Studies show that 80% of users abandon slow websites.
> **Better:** When our product page got two seconds slower in May, checkouts dropped by about a fifth that week. One week, one site, so treat it as a hint.

## 7. Empty wisdom

**Looks like:** sentences shaped like insight that say nothing a reader didn't know. "Success is a journey, not a destination." "The best code is the code you understand." "Communication is the foundation of every team." A paragraph ending on a moral ("And that's the real lesson.").

**Why it reads as slop:** it sounds deep and can't be disagreed with, which is how you know it has no content. Real insight is something a reasonable person could dispute.

**Write instead:** say the specific thing you learned, in a form someone could argue with. If you can't make it arguable, cut it.

> **Slop:** In the end, it's all about putting people first.
> **Better:** We now ship nothing on Fridays. It costs us a day a week, and support tickets on Mondays went down by half.

## 8. Encyclopedia rehash

**Looks like:** the piece opens with a definition ("X is defined as…", "X refers to…"), a potted history ("Since the dawn of the internet…"), or a survey of what everyone knows, before getting to anything new. "X plays a crucial role in Y."

**Why it reads as slop:** the reader came for your case, not a summary they could get anywhere. The rehash is a delay.

**Write instead:** assume the reader knows the basics, or link to a good explainer. Start where your case differs from the textbook.

> **Slop:** Caching is a technique that stores copies of data in a temporary location so that future requests can be served faster.
> **Better:** Our cache was serving logged-in pages to logged-out visitors. Here's the header that did it.

## 9. Coaching voice

**Looks like:** motivational or therapeutic language where nobody asked for it. "You've got this!", "Remember, it's okay to…", "Embrace the journey", "Give yourself grace", "Your feelings are valid". Unearned praise ("Great question!"). Every problem framed as an opportunity.

**Why it reads as slop:** it talks to a generic reader in need of comfort instead of the actual reader with an actual task. In a support reply or a product page, it reads as dodging the problem.

**Write instead:** answer the question, solve the problem, then stop. Warmth comes from being useful and specific, not from reassurance.

> **Slop:** Great question! Feeling stuck is totally normal, and it's all part of the learning journey. Don't give up!
> **Better:** That error means the file is still open in another program. Close it there and run the import again.

## The fix always has two parts

Every finding ends with **a concrete change** (the rewritten line, the cut, the fact to add) and, when the fix needs something only the author knows, **one honest question**. "What did it cost?" is a good question. "Consider adding more detail" isn't a finding.
