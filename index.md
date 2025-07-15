---
layout: default
title: COMP7705 - Agent AI in Stock Market Trading
---



# Agentic AI in Quantitative Trading (Traditional – Cryptocurrency)

> An AI-powered trading analysis system based on a multi-agent architecture. This course project showcases a complete, end-to-end solution for automated financial market analysis, supporting Chinese stocks, US stocks, and major cryptocurrencies.

<a href="https://wp2024.cs.hku.hk/msp24113" class="btn" >Homepage</a> <a href="{{ site.baseurl }}/progress/" class="btn" >Progress</a>

---
## Team Overview

**Group**: msp24113

**Supervisor**: Dr. J.R. Zhang

**Members**:
- Yang Runzhuo – 3036382856
- Lin Xingyan – 3036383020
- Lin Xu – 3036380236
- Liu Rui – 3036380494

---


## Table of Contents

1.  [Project Overview & Background](#-project-overview--background)
2.  [System Architecture](#-system-architecture)
3.  [Multi-Agent Details](#-multi-agent-details)
4.  [Tech Stack](#-tech-stack)
5.  [Core Implementation Details](#-core-implementation-details)
6.  [Usage & Demo](#-usage--demo)
7.  [Summary & Outlook](#-summary--outlook)

---

## Project Overview & Background

The **AI Trading Agent System** is a sophisticated platform designed to simulate a professional investment team. At its core is a **SuperAgent**, an intelligent orchestrator that dynamically manages a team of specialized agents using the **ReAct (Reasoning and Acting)** paradigm. This allows the system to perform complex financial analysis and generate actionable trading insights with human-like adaptability.

The system is built for real-world scenarios, supporting diverse markets including **Chinese A-shares, US stocks, and cryptocurrencies**. It automatically adapts to different market data structures, providing a unified and seamless analysis experience. This project serves as a powerful demonstration for academic research, investment education, and as a robust foundation for future intelligent trading platforms.

### Key Features

-   **SuperAgent as the Core**: The system is driven by a central `SuperAgent` that intelligently orchestrates all other agents, making dynamic decisions based on the ReAct paradigm.
-   **Specialized Multi-Agent Team**: Employs 9+ specialized agents that collaborate in a structured workflow, mirroring a real-world investment team.
-   **Cross-Market Compatibility**: Automatically handles data fetching, normalization, and analysis for stocks and crypto assets from different markets.
-   **Unified Data Pipeline**: Integrates multiple data sources like **Algogene API** and **yfinance**, with standardized data fields for consistent analysis.
-   **End-to-End Workflow**: Covers the entire analysis pipeline from data collection, multi-faceted analysis (technical, fundamental, sentiment), risk assessment, to final decision-making.
-   **Backtesting Engine**: Includes a `backtester.py` module to evaluate agent-driven strategies against historical data across all supported markets.


<img width="1161" height="798" alt="image" src="https://github.com/user-attachments/assets/20d58b94-11cf-4b11-98b5-2d29d5587ce2" />


---

## 🏗System Architecture

The system is designed with a modular, multi-layered architecture that ensures scalability and maintainability. The core components include the orchestration layer, the data layer, the agent layer and the presentation layer (API & CLI).

![System Architecture Diagram](https://github.com/user-attachments/assets/1b9637b8-0db2-454f-8515-c07235f09434)

---

### Orchestration Layer: The SuperAgent

Unlike a static, predefined workflow, our system's process is dynamically managed by the **SuperAgent**. This agent acts as the "brain" of the operation, using the **ReAct (Reasoning and Acting)** framework.

**How it works:**

1.  **Reasoning**: The `SuperAgent` first analyzes the current state of the analysis and the overall goal. It thinks step-by-step about what information is missing and which specialized agent is best suited to perform the next task.
2.  **Acting**: Based on its reasoning, the `SuperAgent` selects and invokes the appropriate agent (e.g., `Technical Analyst`, `Fundamentals Agent`).
3.  **Observation**: It then observes the output from the invoked agent, updates its understanding of the situation, and loops back to the reasoning step.

This dynamic, intelligent orchestration makes the system highly adaptive and robust, capable of handling complex scenarios and unexpected data, much like a human team manager. This is all powered by **LangGraph**, which defines the states and transitions between agents.

---

### Langraph Workflow

The system's workflow is orchestrated by the **SuperAgent** using a graph-based approach (LangGraph). The process is as follows:

1.  **Data Collection**: The `Market Data Agent` fetches and standardizes all necessary data (price, news, financials) for the given ticker.
2.  **Parallel Analysis**: `Technical`, `Fundamental`, `Sentiment`, and `Macro News` agents perform their analysis concurrently.
3.  **Debate & Synthesis**: `Bull` and `Bear Researcher Agents` synthesize the analyses and form opposing arguments, which are then debated in the `Debate Room Agent` to produce a balanced view.
4.  **Risk & Portfolio Management**: The `Risk Management Agent` assesses the trade's risk profile, and the `Portfolio Management Agent` makes the final trading recommendation.
5.  **Output**: The final, comprehensive analysis and recommendation are presented to the user.

---

## Multi-Agent Details

The system's intelligence stems from the collaboration of specialized agents, each with a distinct role:

-   **Market Data Agent**: Gathers and preprocesses all market data.
-   **Technical Analyst Agent**: Performs technical analysis on price data (e.g., MACD, RSI).
-   **Fundamentals Agent**: Analyzes financial metrics and statements.
-   **Sentiment Agent**: Assesses market sentiment from news headlines.
-   **Macro News Agent**: Analyzes macroeconomic news impacting the asset.
-   **Researcher Agents (Bull/Bear)**: Formulate bullish and bearish cases.
-   **Debate Room Agent**: Moderates the debate to form a consensus.
-   **Risk Management Agent**: Evaluates and manages trade risk.
-   **Portfolio Management Agent**: Makes the final investment decision.

---

## Tech Stack

-   **Backend**: Python, FastAPI
-   **AI & Orchestration**: LangChain, LangGraph, Google Gemini
-   **Data Sources**: Algogene API, yfinance, akshare
-   **Frontend**: React, TypeScript, Vite
-   **Dependency Management**: Poetry
-   **Database/Storage**: Local JSON files for caching and state

---

## Core Implementation Details

-   **Automatic Market Dispatch**: The system uses a centralized dispatch logic in `src/tools/api.py`. Based on the ticker format (e.g., numeric for A-shares, alphabetic for US stocks/crypto), it automatically routes requests to the correct data source (yfinance, Algogene, etc.), ensuring seamless cross-market support.
-   **Standardized Data Models**: All data, regardless of the source, is normalized into a standard Pydantic model. This allows agents to process information consistently without needing to know the market of origin.
-   **Explainable AI (XAI)**: By enabling the `--show-reasoning` flag, users can trace the entire decision-making process, viewing the analysis, debates, and conclusions from each agent.

---

## Usage & Demo

### Installation & Configuration

1.  **Install Poetry**:
    ```bash
    curl -sSL https://install.python-poetry.org | python3 -
    ```
2.  **Install Dependencies**:
    ```bash
    poetry install
    ```
3.  **Configure Environment Variables**:
    ```bash
    cp .env.example .env
    # Edit .env and add your API keys
    # GEMINI_API_KEY=your-gemini-api-key
    # ALGOGENE_API_KEY=your-algogene-api-key
    ```

### Command Line Mode

Run comprehensive analysis directly from your terminal.

```bash
# Analyze a US stock
poetry run python src/main.py --ticker TSLA

# Analyze a cryptocurrency with detailed reasoning
poetry run python src/main.py --ticker
#### US Market
**Futu**
Price: 60 usd/mo
Contains: minute level of real time and history data
```

