# Posts in use: one private work archive

Measured on 4 October 2026 in one private work archive that follows [posts](https://github.com/spoj/posts). It describes one setup and compares it with nothing.

**Agents found 87% of the earlier posts their task needed, in an archive of 236 posts.** A missed post changed the outcome in 5 of 35 sampled sessions.

- **Faithful use:** 22 of the 24 sessions that could be judged used what they read faithfully. One slipped slightly and one contradicted its source.
- **Effort:** 23 of 30 sessions reached a relevant post within 5 tool calls of their first archive search; 10 went straight to one.
- **Without help:** with no pointer from the user, agents found 82% of the needed posts. The user pointed the way in 19 of 40 sessions.
- **Superseded posts:** in 19 of the 29 sessions where a relevant post had a newer replacement, the agent read an old version without the new one. Visible harm: once.
- **Linking:** new posts linked or named 78% of the earlier posts a reader would need.
- **Breadth:** a median session drew on 3 kinds of source, 2 of them outside the archive. 73% of sessions went outside it.
- **Session size:** a median session has 5 user messages, 51 model turns and 65 tool calls, runs 30 minutes and costs $2.69 at list prices. The means are far higher (9 messages, 176 turns, 207 tool calls, $17.16): a long tail of big sessions does most of the work, and the top tenth carry 65% of the cost.
- **Scale:** 193 sessions, plus 165 subagent sessions, and 816 commits in 21 days.

Faithful use, effort, help, superseded posts and linking come from a judged sample of 40 sessions and 20 posts. Breadth, session size and scale count every session. Details and method follow.

## The archive

- 236 posts in a private Git repository. 186 were written as dated posts in the 21 days since the archive adopted the format (14 Sep–4 Oct). The other 50 are older material moved into dated folders under their original dates, going back to May 2026.
- 816 commits in those 21 days, with commits on every day; 1,386 since the repository began in May.
- A typical post has 8 files: the README plus evidence and working.
- 86% of the posts written in the period link to at least one other post, and 84% are linked from one.

## The sessions

- 193 sessions started in the archive on 19 of the 21 days, across three computers (plus one session on a fourth). They started 165 subagent sessions.
- Per session, with its subagents included: median 5 user messages, 51 model turns, 65 tool calls and 30 minutes; mean 9 messages, 176 turns and 207 tool calls. The top tenth run past 470 turns and 525 tool calls. Mean duration means little, because some sessions stay open for days.
- Cost per session at list prices, with its subagents included: median $2.69, mean $17.16. The top tenth of sessions carry 65% of the cost. Most tokens are cached input: 5.2 billion cache-read tokens against 27 million output tokens. Sessions used 17 different models.

## How agents use earlier posts

- 61% of sessions open a file in an earlier post, 76% name one somewhere in their tool calls, and 80% search across the archive.
- Re-opened posts are usually recent, with a median age of 4 days. But 31% are over a week old and 21% over 30 days; most of those are the moved-in older material.
- 62% of the posts written in the period were later opened by another session, and 43% by at least two.
- The most re-opened posts are recipes for reaching systems (mail, chat, data sources, tools) and the background of one long-running project, rather than one-off findings.
- 37% of sessions start a post, and 16% start two or more. 44% edit a post begun on an earlier day.

## Retrieval in detail

- 34 of the 40 sampled sessions had a clearly needed earlier post; 30 of them opened at least one.
- The user's pointers were usually in the request. Three came as corrections partway through.
- The five misses that changed the outcome led to redone work, a wrong claim that something couldn't be done, or the user supplying what the post held. Three of the five were posts on how to reach systems.
- Superseded posts are where deferred curation is weakest. Old posts don't link forward, so only a search finds the newer one.
- The 20 sessions that had to search took a median of 4–5 tool calls from their first search; the slowest took 60.
- 8 of 19 new posts missed at least one earlier post a reader would need.

## Where answers come from

- 86% of sessions touched the archive in some way. 73% also went outside it, and 55% reached two or more outside kinds of source: mail, chat, synced company documents, other teams' archives, business systems, the web, local files or pasted screenshots. Each kind appeared in 13–37% of sessions.
- 15% used the archive alone. These were mostly short, cheap exchanges: sessions with an outside source carried 97% of recorded cost.
- The archive is also the map to live sources. 85% of sessions that reached a live company system used one of its posts on how to reach it.
- A median session opened 3 posts, and the top tenth opened 14 or more. Sessions that opened more posts cost more, but only because they were bigger jobs.
- 46% of sessions that fetched outside material saved some of it into a post as evidence, rising to about 80% for the broadest sessions.
- Most outside items were fetched in only one session. 3% of web pages, 7–8% of emails, 11% of company files and 27% of chat threads came up again. When they did, the archive already referenced the item in a quarter to three-fifths of cases, and many repeats were refreshes of things that change.

## How closely agents follow the guide

- The archive root holds only posts, the README and an agent instructions file.
- 85% of folders carry the date of their first commit, and 93% are within a day of it.
- When the guide renamed a post's main file to README.md, half the posts started in the following week still used the old name. The week after, 80 of 82 used README.md.
- READMEs are not short: median 890 words, and over 1,800 for the top tenth. Posts begun since the guide's latest revision are shorter, at a median of about 500 words.
- 92% of links between posts use relative paths, as the guide asks.
- Only 3% of posts were edited a week or more after they were started, though the period is only three weeks.

## Method

- **Counts:** from the repository's history and the agent session logs on each computer. A subagent session counts under the session that started it. Reads, searches and post creation are inferred from tool-call arguments, so they are approximate. Cost is what the session logs record at the provider's list prices.
- **Retrieval sample:** 40 sessions drawn at random across the three computers, and 20 posts written in the period. For each session, the posts it opened were pooled with the top keyword-search hits over the archive as it stood then. One model, which had run only one of the sampled sessions, judged which posts the request needed and how the session used them. A spot check of five judgments agreed with three; the two disagreements changed at most one count.
- **Recall is an upper bound:** a needed post that neither the session nor the keyword search found is not in the pool.
- **Source kinds:** from pattern-matching tool calls. A kind counts if any call touched it, so this measures reach, not reliance. On a hand-labelled held-out sample of 10 sessions, 98% of source-kind decisions agreed.
