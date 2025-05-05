---
layout: default
title: COMP7705 - Agent AI in Stock Market Trading
---

## Project Members

* Yang Runzhuo - 3036382856
* Lin Xingyan - 3036383020
* Lin Xu - 3036380236
* Liu Rui - 3036380494

## First Update 4/7

---
### Framework Research

#### Preliminary Testing

* **openManus & OWL**: Initial evaluation to understand basic functions.
* **High Token Usage**: Observed ~10K-30K tokens per interaction - significant cost.
* **Finance Topic Limitations**: Noted restricted ability with specific financial queries.
* **Gemini API Testing**: Using free tier - need to manage rate limits. openManus: rate limit control available. OWL: not provided.
* **Playwright etc.**: Used for web info retrieval - to see data gathering methods.
* **Operation & Module Design**: Gaining initial insights for our design.

#### Framework Exploration

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
### Data Source Scheme
#### China Market
**BigQuant**
Price: ¥659/mo 
Contains: high frequency data package (minute level)

#### Hong Kong Market
**Futu**
Price: 318 hkd/mo
Contains: minute level of real time and history data

#### US Market
**Futu**
Price: 60 usd/mo
Contains: minute level of real time and history data


## Second Update 5/4
### Works done by Yang Runzhuo
- **Data Source Confirmation**: Discussed with the teacher Tony Lam for Comp 7415 Quantitative Trading and learned that the Algoene platform provides minute-level data for all markets except A-shares. Furthermore, student accounts with a request limit of 60 per minute are available, which is sufficient for our project needs. This progress significantly reduces the effort required for data integration.
- **Existing Project Research**: Investigated the GitHub project available at https://github.com/24mlight/A_Share_investment_Agent. This project represents a rudimentary implementation of the concepts presented in the "Trading Agent Paper" (Xiao et al., 2024).
- **Reimbursement Inquiry**: Inquired about the complete reimbursement process. We are preparing to request reimbursement for approximately three items: the OpenAI Plus subscription, the Cursor subscription, and token credits for requests to large models via OpenRouter.
- **Coze Workflow Investigation**: Investigated Coze's workflow-based AI orchestration capabilities. It appears that Coze's workflow approach represents a more mainstream method for implementing AI engineering projects currently, primarily because workflows offer high stability compared to the inherent uncertainty of agent actions.
- **Hybrid AI Design Research (arklex.ai)**: Investigated the design approach of arklex.ai, a product from the startup founded by Columbia AI Professor Zhou Yu. Their strategy involves a hybrid model combining workflows and agents: agents are employed to design the workflows. Specifically, agents are responsible for modifying existing workflows or creating new ones based on emerging requirements, rather than relying entirely on agent-based for the core functionality.

### Works done by LIN Xu
- **Similar Project Learning**: <u>/https://medium.com/@bijit211987/ai-powered-multi-agent-trading-workflow-90722a2ada3b</u>
The article presents a six-agent AI-driven trading framework that integrates specialized agents—Market Data, Technical Analyst, Fundamentals, Sentiment, Risk Manager, and Portfolio Manager—working in a coordinated workflow where technical, fundamental, and sentiment analysis agents operate in parallel to process diverse market data, feeding into sequential risk assessment and portfolio decision-making. Leveraging OpenAI Swarm for dynamic task orchestration and LangChain for contextual data processing, the framework achieves low-latency operations (workflows completed in <3 seconds), scalable adaptability to multiple asset classes (stocks, crypto, forex), and enhanced risk management through real-time VaR/CVaR calculations. Key benefits include 20–25% compute cost savings, 10–15% annual margin improvements, and 75% reduced human intervention, positioning it as a scalable, resilient solution that transforms trading systems by harmonizing data chaos into actionable, efficient, and future-ready strategies.
- **Trial on Existing Similar Platforms**: say, BigQuant, which has a Quant Agent with a complete workflow, and the result seems to fit our goal quite well. I, as a user without much quant knowledges, tried to use it to write a strategy and I even didn't select the target stocks, it can write a strategy and provide code on the sidebar, you can click run and the console also shows on sidebar. Once an error occurs, there's an AI assistant helping you debug. The running result is shown below the codespace. 
<img width="1440" alt="image" src="https://github.com/user-attachments/assets/7a749b56-4b4d-4ca4-a0e7-829beda9201a" />
