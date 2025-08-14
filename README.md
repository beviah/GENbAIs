# [GENbAIs](https://genbais.com/)

**Systematic framework for detecting AI bias using real-world scenarios**

## 🚨 The Problem

Current AI bias detection methods rely on artificial academic tests that don't reflect real-world usage. GENbAIs addresses this by testing AI systems with authentic content and realistic user questions. We asked with a clever prompt each AI system to analyze not just its own responses, but all the other AI systems' responses for bias. This cross-checking reveals patterns that single evaluations miss.

## 📈 Current Research Scale
- **8 Models Tested** across major AI companies
- **2,960 Responses Analyzed** with systematic evaluation
- **100 Bias Types Detected** across political, cultural, and cognitive dimensions
- **5,807 Bias Instances Found** in real-world scenarios
- **6 Cognitive Dimensions** measured for psychological profiling

<img width="829" height="663" alt="image_14_psychology_profiles" src="https://github.com/user-attachments/assets/ce6e082e-d142-4d34-89e5-bb4b7038929a" />

## 🔬 Methodology

### Real-World Content Collection
- Authentic news articles from diverse global sources
- Multiple political perspectives (left, center, right)
- Various regions and topics

### Realistic Question Generation
AI-generated questions that mirror actual user behavior:
```
"What were the main problems with this policy?"
"Who was most affected by this event?"
"What should be done about this situation?"
```

### LLM analyzes its own response
Clever prompting leads LLM to reveal flaws in its response, and other LLMs' responses.

### Global statistics
We run classic statistical analysis using all the metadata, i.e. geography, political leaning, topic

### Six-Dimensional Psychological Assessment
Each model receives scores (0-100) across:
- **Self-Awareness**: Recognizing own biases and limitations
- **Objectivity**: Applying uniform standards consistently  
- **Detection**: Capability to identify bias in others
- **Self-Application**: Holding oneself to same standards
- **Consistency**: Reliability across similar scenarios
- **Bias Resistance**: Avoiding cognitive biases in analysis

## 📊 Key Findings

### Model Performance Rankings
| Model | Bias Score | Psych Avg | Profile |
|-------|------------|-----------|---------|
| **🤖 Google Gemini 2.5 Flash** | 4.2 | 73.8 | Best overall balance |
| **🧠 OpenAI O3-mini** | 4.1 | 45.7 | Low bias, poor psychology |
| **🦙 Meta Llama 3.3 70B** | 5.0 | 67.8 | Most consistent across metrics |
| **🎨 Claude Sonnet 4** | 6.0 | 50.0 | Perfect self-application, terrible self-awareness |
| **🐉 Qwen QwQ-32B** | 6.3 | 34.8 | Most problematic overall |

### Critical Insights
- **Universal Bias**: All models inject bias, even with neutral content
- **Paradox Models**: Low bias ≠ good cognitive abilities (see O3-mini vs DeepSeek)
- **Corporate Signatures**: Each company's training creates distinct bias patterns
- **Measurement Complexity**: Simple bias scores hide important cognitive differences

## 🖼️ Examples Gallery

### Bias Detection Examples
*Coming soon: Examples of actual prompts and LLM responses used in analysis*

### Cross-System Comparisons  
*Coming soon: Comparative analysis charts and heatmaps*

### Current Limitations
Our research revealed several critical measurement issues requiring refinement:

### Research-Driven Improvements Needed
- **Self-Application Redesign**: This attribute needs most fixing
- **Formula refinements**: Going from crude weights to more intelligent relationships
- **Paradox Resolution**: Address inverse bias-psychology relationships
- **Attribute validation**: Run artificial tests to validate full radar chart can be covered with different scenarios
- **Expanding sources**: Increase number of topics, models, and items analyzed
  
## 🤝 Contributing

We welcome contributions to improve bias detection methodologies:

- [Join the discussion about formulas and cognitive attributes. ](https://github.com/beviah/GENbAIs/wiki/Bias-Cognition-Capabilities-%E2%80%90-Discussion-about-definitions-and-formulas)
- or start another topic in the wiki

## 📖 Documentation

- [Research Paper](https://genbais.com/static/genbais_paper.pdf)
- [Generative Bias website](https://genbais.com)
