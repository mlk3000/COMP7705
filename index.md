---
layout: default
title: COMP7705 - Agent AI in Stock Market Trading
---

## Project Members

* Yang Runzhuo - 3036382856
* Lin Xingyan - 3036383020
* Lin Xu - 3036380236
* Liu Rui - 3036380494

## Fourth Update 7/7

### Works done by Yang Runzhuo
- Exploration of Advanced AI Development Tools:

    Gained proficiency in using Claude Code for efficient code generation and development assistance.

- Mastered the implementation of sophisticated agent models using LangChain, focusing on two key architectures:

    ReAct Framework: Developed an understanding of how to build agents that synergize reasoning and action to robustly handle tasks.
    Plan-and-Execute Model: Learned to construct agents that first formulate a multi-step plan and then execute it, enhancing the reliability of complex workflows.

### Works done by Lin Xu
- Studied RAG and explored new feature directions:
Focused on applying Retrieval-Augmented Generation to build a financial knowledge base, aiming to improve accuracy in domain-specific responses of agents.
- Explored quantitative trading strategies:
Learnt common strategies and considered how agents can recommend suitable ones and perform backtesting.
- Analyzed existing Trading Agent implementations:
Investigated other trading agent practices to evaluate their effectiveness and gather ideas for our own system.

### Works done by Lin Xingyan

- Integrated Algogene US Stock Data: Incorporated and refined the use of Algogene's core OHLCV data for US equities.

- Optimized Data Sourcing: Strategically allocated data acquisition, leveraging Algogene for its intraday granularities while complementing with yFinance for broader financial data.

- Enhanced Macro News Agent: Extended the agent's capabilities through the integration and refinement of Algogene's macro news API.
---
## Third Update 6/16 (After the Interium Report)

### Works done by Yang Runzhuo
- Secured 5,000 HKD in credits from Algoene, which provides us with access to their data API and a testing account.
- Explored a hybrid framework integrating LangGraph and AutoGen to leverage the respective strengths of dynamic, tool-using multi-agent collaboration and structured, graph-based workflows.
- Organized a mid-term development meeting to define and assign development tasks for each team member.

### Works done by LIN Xu
- Add Algogene as a data source, capable of fetching minute-level historical market quotes and real time data

### Works done by LIN Xingyan
- Enhanced Macro News Agent: Conducted comprehensive testing and iterative modifications to the macro news agent's logic.
- Stabilized Daily Backtester: Addressed and resolved issues within the daily backtester, ensuring its reliable and accurate execution.
- Streamlined Langgraph Data Handling: Reworked data structures for message passing within Langgraph, preventing duplicate data appending by agents.
![Figure_2](https://github.com/user-attachments/assets/a0c4cd67-9f44-4bad-bba2-d455d157e395)

- Future Initiatives
   - Integrate AlgoGene data to build out our analysis capabilities for US stocks and Cryptos. (Closer)
   - Support more frequent trading by using finer-interval data, moving beyond our current daily focus. (Further)

### Works done by LIU Rui
- A chatbot has been designated as the primary user interface, with React determined as the development technology. The preliminary design of the required ports for the interface and the page design style has been essentially determined.

---

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

### Works done by LIU Rui
- **Quantitative trading system development framework**: Learned about VeighNa, an open source Python-based framework for developing quantitative trading systems  <u>https://github.com/vnpy/vnpy</u>. Currently it provides a variety of modules, including a multi-functional quantitative trading platform (integrating a variety of trading interfaces and providing a simple and easy-to-use API for the development of specific strategy algorithms and functions), a CTP trading interface covering domestic futures and options trading in China, adapted to SQLite, and docked to the RQData (which is able to provide relevant data services for stocks, futures, options, funds, bonds, and gold TD). data service). Currently deployed on Windows and Ubantu systems (in progress).
<img width="1120" alt="vnpy" src="https://github.com/user-attachments/assets/8d578090-4979-4f06-9bb5-1c7b5c9dd64f" />

### Works done by LIN Xingyan

- Looked into a financial LLM framework proposed by SUFE (arXiv:2503.16252v1), which finetunes on a financial reasoning dataset and applies reinforcement learning to improve interpretability and decision-making. Although it proposes a training-based approach, some voices argue that effective agent design relies more on leveraging contextual information rather than fine-tuning.
- Followed a basic trading bot tutorial to get a general sense of how signal generation and agent execution flow are typically structured.
- [Learned about a personally-built end-to-end trading platform](https://mpmt.notion.site/1e8cc64d809c80bb8d3de53ec6c9c8d6), with a focus on how the author integrated various published backtesting models into a functional and client-ready codebase.
- Explored Coze’s access to Huatai-exclusive data to understand how to fetch structured research reports, analyze sectors, and incorporate this into agent-driven investment analysis, with workflows and analysis methods that can be adapted.
![image](https://github.com/user-attachments/assets/32af371a-c942-4d66-9489-65d50b1d63d7)

---
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

