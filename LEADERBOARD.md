# The AI-Visibility Index

Which sources AI assistants actually cite when buyers ask for the best option in a category. Measured, dated, versioned and open. This is the standing, human-readable index; the machine-readable counts are in [`data/`](data/).

It measures **what AI cites**, which is the observable, checkable thing. "What AI cites" is upstream of "which product AI names": if a source is never cited in a category, nothing on it can be named from it. New categories are added as they are measured. To have your category measured, open an issue.

Maintained by the team behind [Glotier](https://glotier.com). We publish the index whether or not it flatters us; in the category below, our own domain is not cited at all, and that is in the data too.

---

## AI-visibility and SEO tools

*21 buying questions, put to ChatGPT, Gemini and Perplexity as live web queries, 20–26 July 2026. Counted per answer: a source cited by an answer counts once for that answer, not per mention. 93 distinct domains appeared across the 21 answers; the tables show every domain cited in 4 or more of them. Source: [`data/which-sources-ai-cites.csv`](data/which-sources-ai-cites.csv).*

### Community and platforms

| Source | Answers cited in (of 21) |
|---|---|
| reddit.com | 12 |
| youtube.com | 4 |

### Tools and vendors

| Source | Answers cited in (of 21) |
|---|---|
| rankability.com | 7 |
| frase.io | 6 |
| semrush.com | 6 |
| seranking.com | 5 |
| tryprofound.com | 5 |
| alhena.ai | 4 |
| dageno.ai | 4 |
| gracker.ai | 4 |
| nightwatch.io | 4 |
| useomnia.com | 4 |
| wpengine.com | 4 |
| zapier.com | 4 |

**The single most-cited source in the category is a community forum, not a vendor.** Reddit was cited in 12 of 21 answers, more than any tool. That is the recurring pattern across every category we have measured: see [`data/sources-by-type.csv`](data/sources-by-type.csv), where community sources outweigh the paid review directories 21 to 1.

---

## Gatekeepers by category

The one domain cited in **every** answer of a category, plus Reddit's share, from a 3-category study (6 buying questions each, 26 July 2026). When a single source feeds all six answers, it is effectively the gate you have to get through to appear in that category at all.

| Category | Reddit share | Gatekeeper (cited in all 6 answers) |
|---|---|---|
| AI SEO tools | 2 of 6 | onelittleweb.com |
| Email marketing software | 4 of 6 | emailvendorselection.com |
| Help desk software | 6 of 6 | reddit.com |

In help desk software the gatekeeper *is* Reddit: every answer leaned on it. In the other two, a single roundup article (onelittleweb.com, emailvendorselection.com) fed every answer, which means one page decides who gets named. Getting onto that one page is the whole game in those categories.

## How this index is built, and its limits

Every figure is re-derivable. Each buying question is asked as a live web query, the sources behind each answer are recorded, and domains are counted once per answer. The window and question count are stated for each category so a reader can reproduce it. Samples are deliberately small and named rather than large and vague; the value is that the raw counts are public.

This index tracks **citation**, not endorsement, and not crawl access. A domain cited often is a domain the assistants lean on to build answers in that category, which is where the competition for a mention actually happens.

## Related

- [Glotier](https://glotier.com) runs this measurement continuously, with a free page-readiness check.
- The full method write-ups: [what sources AI cites](https://glotier.com/guides/what-sources-ai-cites) and [where AI answers come from](https://glotier.com/guides/where-ai-answers-come-from).
