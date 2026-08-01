# AI Visibility Data

Open datasets on **which sources AI assistants cite**, **which AI crawlers can read the web**, and **how much the assistants disagree**. Measured directly, published with the method and the limits so you can check every number rather than take our word.

Maintained by the team behind [Glotier](https://glotier.com), an AI-visibility measurement tool. The numbers here are the same measurements Glotier runs on itself and its own category, published openly. Where a figure flatters no one, it is here anyway.

## Why this exists

When someone asks ChatGPT, Gemini or Perplexity for the best tool in a category, the answer is assembled from a small set of sources the model retrieved and trusted. Almost nobody has published raw counts of **which** sources those are. This repository does, for a handful of software categories, so that anyone optimizing for AICitation can work from evidence instead of folklore.

Two words that get conflated and should not be: **allowed** (a permission you wrote in `robots.txt`) and **crawled** (an event in your server logs). Only one of them shows up in your logs.

## Datasets

| File | What it is | Measured | Sample |
|---|---|---|---|
| [`data/which-sources-ai-cites.csv`](data/which-sources-ai-cites.csv) | Domains cited across 21 buying questions in the AI-SEO/visibility category, counted per answer | 20–26 Jul 2026 | 21 questions, 93 distinct domains |
| [`data/sources-by-type.csv`](data/sources-by-type.csv) | Community vs review-directory citations across 3 software categories | 26 Jul 2026 | 18 answers, 131 citations |
| [`data/ai-crawlers-reference.csv`](data/ai-crawlers-reference.csv) | The AI crawler user-agents, their job, and whether the operator publishes a verifiable IP-range file | 31 Jul 2026 | 13 agents, 6 operators publishing ranges |
| [`data/ai-crawler-access.csv`](data/ai-crawler-access.csv) | Of the domains assistants actually cite, how many let the AI crawlers in | 31 Jul 2026 | 259 cited domains |
| [`data/model-disagreement.json`](data/model-disagreement.json) | How often ChatGPT, Gemini and Perplexity name the same products, including on identical sources | 19 Jul 2026 | 39 questions, 437 products |
| [`data/one-slot-per-domain.json`](data/one-slot-per-domain.json) | Whether a domain can appear more than once in a single Google AI answer | 31 Jul 2026 | 13 answers, 168 citations |

## Headline findings

- **Community beats directories, by a lot.** In a study across 3 software categories (18 answers, 131 citations counted per answer, 26 Jul 2026), community forums (Reddit, Quora, Hacker News, Stack Overflow, YouTube, Medium) were cited **21 times** more often than the classic review directories, which were **0.8%** of all citations. See [`data/sources-by-type.csv`](data/sources-by-type.csv).
- **Reddit is a gatekeeper.** In a separate study of 21 buying questions in the AI-visibility category (20–26 Jul 2026), Reddit was a source in **12** of them, cited more often than any vendor. See [`data/which-sources-ai-cites.csv`](data/which-sources-ai-cites.csv).
- **One slot per domain.** Across 13 Google AI answers and 168 citations, **not one domain appeared twice**. AI answers are not a ranked page where a strong domain takes several spots; they gather one best page per sub-question.
- **The assistants disagree more than you would think.** Only **30%** of named products were named by all three assistants; **47%** were named by exactly one. Handed identical sources, ChatGPT and Gemini still agreed only **64%** of the time, so a share of whether you get named is the model, not the source.
- **Not every crawler can be verified.** Some operators publish an IP-range file you can check a request against; Meta and Amazon publish none, and Google publishes for Googlebot but nothing that isolates `Google-Extended`, so a large share of AI-crawler requests cannot be matched to a published range. See [`data/ai-crawlers-reference.csv`](data/ai-crawlers-reference.csv).

## Method, in short

Each buying question is put to the assistants as a live web query, and every source behind every answer is recorded. Counting is **per answer, not per mention**: a page a single answer leans on three times is one answer's worth of evidence, because counting repeats would measure one model's verbosity instead of the category's citation surface. Access figures are parsed with the same robots.txt logic a browser would apply, so a path-only disallow is not counted as a block, which means the access numbers understate blocking rather than overstate it.

Samples are small and named. A finding from 13 answers is labelled as a finding from 13 answers. The point is not a large N; it is that the raw counts are public and reproducible.

## Reproduce it

Every number is re-derivable. Take five buying questions in your category, put each to ChatGPT, Gemini and Perplexity, and record the sources behind each answer. Count how many distinct domains appear, how many appear in only one assistant, and how many appear more than once in a single answer. If your counts differ from ours, open an issue with the questions and we will compare.

## Related

- [Glotier](https://glotier.com) — the tool that runs these measurements, with a free page-readiness check.
- [Glotier: what sources AI cites](https://glotier.com/guides/what-sources-ai-cites) and [how assistants disagree](https://glotier.com/guides/how-assistants-disagree) — the write-ups behind this data.
- [awesome-generative-engine-optimization](https://github.com/oguzhanglotier/awesome-generative-engine-optimization) — tools, standards and references.
- [ai-readiness-check](https://github.com/oguzhanglotier/ai-readiness-check) — a small CLI to check whether AI crawlers can read a given site.

## License

Data is licensed [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/): use it, remix it, publish it, with attribution to Glotier and a link back to this repository.
