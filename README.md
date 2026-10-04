# evals

Measurements of two patterns for agent work in real use: [posts](https://github.com/spoj/posts), a format for an agent's work archive, and [recon](https://github.com/spoj/recon), a pattern for reconciliations. Each dated folder is one measurement, written as a post. The data measured is private, so posts here carry aggregate numbers only.

| Post | Headline |
|---|---|
| [Posts in use: one private work archive](2026-10-04-one-work-archive/README.md) | Agents found 87% of the earlier posts their task needed, in an archive of 236 posts. |
| [Garbage in, garbage out? Fact recall in a minimally organized archive](2026-10-04-fact-recall/README.md) | With a dated folder and a README per post, no index and no purging, an agent found 99% of single facts and 97% of a 144-question set; archive lookups took 7.8% of what 193 real sessions spent. |
| [Does a reconciliation pattern help a strong agent? Not in one shot](2026-10-04-recon-benchmarks/README.md) | Pointed at spoj/recon, gpt-6.1-sol did no better in two real reconciliations: a 136-line bank rec was perfect either way, and on 16,933 intercompany items both arms left the expert a list of similar quality, while recon took more time and tokens. Cut to code alone, the repo kept most of recon's caution at about flat's time and cost. |
