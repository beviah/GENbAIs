```markdown
# Bootstrapped LLM Bias Dataset

This repo demonstrates how to bootstrap a bias-detection and mitigation dataset from noisy LLM evaluations over real-world news articles. It is **not** a gold-standard benchmark; it is an instructive case study of how such pipelines work and where they fail.

## Overview

We start from multi-model bias annotations on sentences drawn from news coverage spanning seven political leanings (far-left to far-right). A builder script cleans and restructures this data into several supervision-ready JSONL files (critics, contrastive pairs, mitigation SFT), and an analysis script profiles the behavior of the underlying evaluator models.

The aim is to show:

- How to turn messy LLM bias analyses into usable training data.
- How to detect common pathologies (ideological skew, label monoculture, density saturation).
- How to design multiple tasks (critic, embeddings, rewrites) from one shared corpus.

## Pipeline (high level)

1. **Collect raw annotations**  
   - Sentence-level bias scores and types from multiple LLMs on news stories with political lean metadata.

2. **Clean and filter**  
   - Remove junk, evaluator prompts, diagnostic scaffolding, and meta-analysis sentences that talk *about* bias instead of containing it.  
   - Deduplicate similar sentences within each analysis.

3. **Balance and aggregate**  
   - Balance samples across political lean categories.  
   - Merge multiple labels per sentence and aggregate sentences into response-level groups with a bias density signal.

4. **Generate task-specific datasets**  
   - Sentence-level critics (single- and multi-label).  
   - Contrastive pairs/triplets for embeddings.  
   - Response-level critics with bias density.  
   - Mitigation SFT data (biased sentence → debiased rewrite).

5. **Profile model behavior**  
   - For each evaluator model, compute a compact “behavioral fingerprint” (score levels, variance, label diversity, ideological sensitivity, density patterns).

## Key Findings (qualitative)

- **Compressed scoring:** Evaluators rarely use the full score range, limiting contrast for training.  
- **Label monoculture:** Some models heavily overuse a single bias type, reducing taxonomic coverage.  
- **Ideological sensitivity:** Certain models conflate political orientation with bias severity more than others.  
- **No cross-rater ground truth:** Each sentence is labeled by a single model, so inter-rater agreement cannot be measured.

These findings are meant to warn that naive use of LLM critics can *import* their own biases into downstream models.

## Files (conceptual)

- **Data builder script**  
  - Takes raw JSON/JSONL bias annotations (plus optional HTML cases) and writes multiple cleaned JSONL datasets + a small quality report.

- **Analysis script**  
  - Reads the sentence- and response-level critic datasets and produces per-model profiles and a JSON summary report.

- **Output datasets** (JSONL)  
  - Sentence-level critics.  
  - Response-level critics.  
  - Contrastive pairs and triplets.  
  - Debias-rewrite SFT examples.

## Intended Use

This repo is intended as:

- A **worked example** of bootstrapping supervision from noisy LLM outputs.  
- A **teaching/diagnostic tool** for understanding LLM-based bias detection, not a production-ready debiasing dataset.  

If you build on this, you should treat the labels as weak supervision and re-run profiling whenever you change data sources, models, or sampling rules.
```
