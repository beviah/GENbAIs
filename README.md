# [GENbAIs](https://genbais.com/) — Bio-Inspired Adapters: Improving Models Beyond LoRA Fine-Tuning

**General Efficient Neural bio-Adapter Intelligent Search**

Intelligent search over 50+ neuroscience-inspired mechanisms discovers lightweight adapters that improve foundation models beyond state-of-the-art parameter-efficient fine-tuning. Validated on 20 benchmarks — **17 wins, 3 losses**.

### 🤗 [Model on HuggingFace](https://huggingface.co/lakinekaki/all-MiniLM-L6-v2-genbais) · 🌐 [Website](https://genbais.com) · 📄 [Paper](https://genbais.com/static/genbais_paper.pdf)

---

## 📊 Benchmark Results

**all-MiniLM-L6-v2 + GENbAIs Bio Adapters** vs baseline sentence-transformers/all-MiniLM-L6-v2:

| | Value |
|---|---|
| **Average improvement** | +0.0205 (absolute, across 20 metrics) |
| **Win rate** | 85% — 17 wins / 3 losses |
| **Best single gain** | +14.66% (PAWS adversarial paraphrase) |
| **Experiments run** | ~1,000 out of 10²² possible configurations |

### Semantic Textual Similarity

| Dataset | Baseline | Enhanced | Δ% |
|---------|----------|----------|----|
| stsb | 0.8203 | 0.8524 | **+3.91%** |
| sts13 | 0.8060 | 0.8602 | **+6.72%** |
| sts14 | 0.7559 | 0.8311 | **+9.95%** |
| sts16 | 0.7899 | 0.8174 | +3.48% |

### Pair Classification

| Dataset | Metric | Baseline | Enhanced | Δ% |
|---------|--------|----------|----------|----|
| **paws** | **ap** | **0.5844** | **0.6701** | **+14.66%** |
| paws | f1 | 0.6140 | 0.6495 | +5.79% |
| mnli | ap | 0.6070 | 0.6415 | +5.68% |
| mrpc | ap | 0.8369 | 0.8586 | +2.59% |

### Clustering

| Dataset | Baseline | Enhanced | Δ% |
|---------|----------|----------|----|
| twentynewsgroups | 0.4894 | 0.5053 | **+3.24%** |

> Full results with all 20 metrics at [genbais.com](https://genbais.com/#benchmarks)

---

## 🧬 How It Works

### 1. Bio-Feature Library (50+ mechanisms)
Lightweight adapter modules inspired by neuroscience — predictive coding, lateral inhibition, Hebbian learning, dendritic computation, homeostatic scaling, and more. Each adds up to ~1% of model parameters.

### 2. Intelligent Search (Thompson Sampling)
The configuration space is ~10²² possibilities. We use Thompson sampling with Bayesian pruning to find optimal combinations in ~1,000 experiments — exploring 0.00000000000000001% of the space.

### 3. Stacked on Best LoRA
Bio adapters are stacked on top of the optimal LoRA configuration, proving they provide **additive improvement beyond state-of-the-art PEFT**.

### 4. Distillation
The enhanced model is distilled into a clean SentenceTransformer — **no custom code needed to load**:

```python
from sentence_transformers import SentenceTransformer

model = SentenceTransformer("lakinekaki/all-MiniLM-L6-v2-genbais")
embeddings = model.encode(["Hello world", "Bio-inspired AI enhancement"])
```

---

## 🔑 Key Insights

- **🪨 Hard-mode validation**: all-MiniLM-L6-v2 is a 22M-param, 6-layer model already distilled and heavily optimized by the sentence-transformers team — one of the toughest targets to improve. Larger models (CLIP, LLaMA, Mistral) with more layers and parameters offer significantly more room for bio-adapter gains.
- **Adversarial robustness**: Largest gains on PAWS (+14.7%) — bio features capture semantic structure beyond lexical overlap
- **Broad improvement**: Gains across STS, pair classification, AND clustering — not task-specific overfitting
- **Additive over LoRA**: Bio mechanisms find optimization directions that standard PEFT misses
- **Efficient exploration**: ~1,000 experiments find performing configurations surpassing LoRA out of 10²² possible

---

## 🔍 Related Research: AI Bias Detection

GENbAIs bio-adapter enhancement is built on systematic AI bias research. By understanding how AI systems exhibit cognitive biases, we design better mechanisms to correct them.

### UPDATE: [genbais.com](https://genbais.com/) has been removed from Google index — apparently they do not like their biases exposed!

### Research Scale
- **8 Models Tested** across major AI companies
- **2,960 Responses Analyzed** with systematic evaluation
- **5,807 Bias Instances Found** in real-world scenarios
- **6 Cognitive Dimensions** measured for psychological profiling

### Model Bias Rankings
| Model | Bias Score | Psych Avg | Profile |
|-------|------------|-----------|---------|
| Google Gemini 2.5 Flash | 4.2 | 73.8 | Best overall balance |
| OpenAI O3-mini | 4.1 | 45.7 | Low bias, poor psychology |
| Meta Llama 3.3 70B | 5.0 | 67.8 | Most consistent |
| Claude Sonnet 4 | 6.0 | 50.0 | Perfect self-application, terrible self-awareness |
| Qwen QwQ-32B | 6.3 | 34.8 | Most problematic |

### Methodology
- Real-world news articles across political perspectives and regions
- Realistic user questions (not artificial benchmarks)
- Cross-model evaluation — each AI analyzes all others' responses
- Six-dimensional cognitive profiling

> Full bias results: [genbais.com/examples](https://genbais.com/examples/)

### Also see: [Frac⛏️ure](https://github.com/beviah/fracture) — AI stress testing framework

---

## 🤝 Contributing

- [Discussion: bias formulas and cognitive attributes](https://github.com/beviah/GENbAIs/wiki/Bias-Cognition-Capabilities-%E2%80%90-Discussion-about-definitions-and-formulas)
- [LLM introspection prompt gallery](https://github.com/beviah/GENbAIs/wiki/LLM-introspection-PROMPT-gallery)

## 📖 Links

- 🤗 [HuggingFace Model](https://huggingface.co/lakinekaki/all-MiniLM-L6-v2-genbais)
- 🌐 [Website & Benchmarks](https://genbais.com)
- 📄 [Research Paper](https://genbais.com/static/genbais_paper.pdf)

## License

MIT
