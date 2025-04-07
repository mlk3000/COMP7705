---
layout: default
title: COMP7705 - Agent AI in Stock Market Trading
---

## Project Members

* Yang Runzhuo - 3036382856
* Lin Xingyan - 3036383020
* Lin Xu - 3036380236
* Liu Rui - 3036380494

## Block 1

---
## Framework Research

### Preliminary Testing

* **openManus & OWL**: Initial evaluation to understand basic functions.
* **High Token Usage**: Observed ~10K-30K tokens per interaction - significant cost.
* **Finance Topic Limitations**: Noted restricted ability with specific financial queries.
* **Gemini API Testing**: Using free tier - need to manage rate limits. openManus: rate limit control available. OWL: not provided.
* **Playwright etc.**: Used for web info retrieval - to see data gathering methods.
* **Operation & Module Design**: Gaining initial insights for our design.

### Framework Exploration

* **MetaGPT**:
    * **Software Company Simulation**: Model based on roles within a company.
    * **Rapid Code & Doc Generation**: Quick output for strategy development.
    * **Static Development**: Best for predefined tasks.
* **AutoGen**:
    * **Agent Collaboration**: Focus on agents working together.
    * **Simple Web GUI**: Interface for easier interaction.
    * **Real-time Data & Full Process**: Flexible for dynamic data and the whole system.

* **Trading Agent Paper (Xiao et al., 2024)**: This paper's work focuses on improving information interaction methods and defining roles within MetaGPT. The authors claim the code will be open-source but it is not yet uploaded.


---
## Data Source Scheme
### China Market
**BigQuant**
Price: ¥659/mo 
Contains: high frequency data package (minute level)

### Hong Kong Market
**Futu**
Price: 318 hkd/mo
Contains: minute level of real time and history data

### US Market
**Futu**
Price: 60 usd/mo
Contains: minute level of real time and history data
