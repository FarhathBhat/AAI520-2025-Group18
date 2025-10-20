# Agentic AI Financial Analysis System

## 🎓 University Project - AAI520 Group 18

An autonomous investment research agent powered by artificial intelligence that performs comprehensive financial analysis on publicly traded stocks using real-time market data.

---

## 📋 Table of Contents
- [Project Overview](#project-overview)
- [Key Features](#key-features)
- [System Architecture](#system-architecture)
- [Installation](#installation)
- [Usage](#usage)
- [Agent Capabilities](#agent-capabilities)
- [Workflow Patterns](#workflow-patterns)
- [Evaluation Criteria](#evaluation-criteria)
- [Requirements](#requirements)
- [Team](#team)

---

## 🎯 Project Overview

This system implements an **Investment Research Agent** that operates autonomously to analyze stocks through:
- Dynamic tool selection and execution
- Multi-stage analysis pipelines with quality evaluation
- Self-reflection mechanisms for continuous improvement
- Memory persistence for cross-run learning

The agent processes real financial data from Yahoo Finance to generate data-driven investment recommendations with transparent reasoning and confidence metrics.

---

## ✨ Key Features

### 🤖 Autonomous Agent Functions
- **Self-Planning**: Plans research steps before execution
- **Dynamic Tool Usage**: Selects appropriate analysis tools based on requirements
- **Self-Reflection**: Evaluates its own output quality
- **Learning System**: Improves performance across multiple analyses

### 🔄 Three Workflow Patterns
1. **Prompt Chaining**: Sequential processing (Ingest → Preprocess → Classify → Extract → Summarize)
2. **Intelligent Routing**: Task distribution to specialized agents (earnings, technical, sentiment, fundamental)
3. **Evaluator-Optimizer**: Continuous refinement (Generate → Evaluate → Refine)

### 📊 Real-Time Analysis
- Live stock prices and market data
- Historical price trends and volatility
- Fundamental metrics (P/E ratio, market cap, dividend yield, etc.)
- Risk assessment and sentiment analysis
- Investment recommendations (BUY/SELL/HOLD)

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                  Investment Research Agent                   │
│                                                              │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │   Planning   │→ │  Execution   │→ │  Reflection  │     │
│  │    Module    │  │    Engine    │  │   & Learning │     │
│  └──────────────┘  └──────────────┘  └──────────────┘     │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                    Workflow Layer                            │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │   Prompt     │  │   Routing    │  │  Evaluator-  │     │
│  │   Chaining   │  │   System     │  │  Optimizer   │     │
│  └──────────────┘  └──────────────┘  └──────────────┘     │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                     Tool Layer                               │
│  ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐       │
│  │Financial│  │Fundamen-│  │Sentiment│  │  Risk   │       │
│  │  Data   │  │  tals   │  │Analysis │  │Assessment│      │
│  └─────────┘  └─────────┘  └─────────┘  └─────────┘       │
└─────────────────────────────────────────────────────────────┘
                              ↓
                    ┌──────────────────┐
                    │  Yahoo Finance   │
                    │   (Real Data)    │
                    └──────────────────┘
```

---

## 🚀 Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager
- Internet connection (for fetching real-time data)

### Setup Instructions

1. **Clone the repository**
```bash
git clone https://github.com/FarhathBhat/AAI520-2025-Group18.git
cd AAI520-2025-Group18
```

2. **Install required packages**
```bash
pip install yfinance pandas numpy
```

3. **Open in Google Colab (Recommended)**
- Upload the `.ipynb` file to Google Colab
- Run all cells sequentially

**OR**

3. **Run locally with Jupyter**
```bash
pip install jupyter
jupyter notebook
```

---

## 💻 Usage

### Basic Usage

```python
# Initialize the agent
agent = InvestmentResearchAgent()

# Run complete analysis on a stock
agent.run_full_analysis("AAPL")

# The agent will:
# 1. Plan its research strategy
# 2. Execute all three workflow patterns
# 3. Generate quality-assessed recommendations
# 4. Learn from the analysis for future runs
```

### Analyzing Multiple Stocks

```python
stocks = ["AAPL", "MSFT", "GOOGL", "TSLA", "AMZN"]

for stock in stocks:
    agent = InvestmentResearchAgent()
    agent.run_full_analysis(stock)
    print(f"\nCompleted analysis for {stock}\n" + "="*70)
```

### Accessing Agent Memory

```python
# View agent's self-reflection
print(agent_memory.reflect_on_performance())

# Check learned strategies
strategy = agent_memory.get_learned_strategy("AAPL")
```

---

## 🧠 Agent Capabilities

### 1. Dynamic Tool Selection
The agent intelligently selects from four specialized tools:

| Tool | Purpose | Key Metrics |
|------|---------|-------------|
| **Financial Data** | Price & market data | Current price, 52-week high/low, volatility |
| **Fundamentals** | Financial health | P/E ratio, ROE, debt-to-equity, profit margins |
| **Sentiment** | Market perception | News sentiment, price momentum |
| **Risk Assessment** | Investment risk | Risk score (0-10), volatility, risk factors |

### 2. Self-Reflection Mechanism
- Evaluates analysis quality (0-10 scale)
- Identifies data gaps and completeness issues
- Assigns confidence levels (High/Moderate/Low)
- Tracks success rates across analyses

### 3. Learning System
- Records all analyses with quality scores
- Stores successful strategies for similar stocks
- Logs failures to avoid repeated mistakes
- Generates performance reflection reports

---

## 🔄 Workflow Patterns

### Pattern 1: Prompt Chaining
Sequential 5-stage pipeline:
```
Ingest Data → Preprocess → Classify → Extract Insights → Summarize
```

### Pattern 2: Intelligent Routing
Directs analysis to specialized agents:
- **Earnings Specialist**: EPS, revenue, profit margins
- **Technical Specialist**: Price trends, volatility, momentum
- **Sentiment Specialist**: Market perception, news analysis
- **Fundamental Specialist**: Valuation, financial health

### Pattern 3: Evaluator-Optimizer
Continuous improvement loop:
```
Generate Analysis → Evaluate Quality → Refine Output → Re-evaluate → Learn
```

---

## 📊 Evaluation Criteria

This project is evaluated on three components:

| Component | Weight | Implementation |
|-----------|--------|----------------|
| **Agent Functions** | 33.8% | Planning, dynamic tools, self-reflection, learning |
| **Workflow Patterns** | 33.8% | Prompt chaining, routing, evaluator-optimizer |
| **Code Quality** | 32.4% | Structure, documentation, efficiency, error handling |

---

## 📦 Requirements

### Core Dependencies
```
yfinance>=0.2.0
pandas>=1.3.0
numpy>=1.21.0
```


### Python Version
- Python 3.8+

---

## 📈 Sample Output

```
======================================================================
RESEARCH PLAN FOR AAPL
======================================================================
  Step 1: Execute prompt chain (ingest → analyze → classify)
  Step 2: Route to specialist agents
  Step 3: Generate and optimize analysis
  Step 4: Self-reflect on quality and recommendations

**********************************************************************
WORKFLOW 1: PROMPT CHAINING
**********************************************************************
[Chain Stage 1] Ingesting data for AAPL...
[Chain Stage 2] Preprocessing data...
[Chain Stage 3] Classifying stock characteristics...
[Chain Stage 4] Extracting investment signals...
[Chain Stage 5] Generating chain summary...

======================================================================
AGENT SELF-REFLECTION & RECOMMENDATIONS
======================================================================
SELF-REFLECTION REPORT FOR AAPL:
- Analysis Quality Score: 8.5/10
- Confidence Level: High confidence
- Investment Recommendation: BUY

REASONING:
  • Fair valuation: P/E ratio of 28.3
  • Strong dividend yield: 0.52%
  • Positive market sentiment (2 positive vs 0 negative)
  • High confidence analysis (Quality: 8.5/10)
```

---

## 🎓 Educational Value

This project demonstrates:
- **AI Agent Design**: Autonomous decision-making and planning
- **Workflow Orchestration**: Multiple processing patterns working in concert
- **Quality Assurance**: Self-evaluation and iterative refinement
- **Machine Learning**: Learning from experience across runs
- **Financial Analysis**: Real-world application of AI to investment research

---

## 🔮 Future Enhancements

- [ ] Integration with NewsAPI for real-time news sentiment
- [ ] Addition of FRED API for economic indicators
- [ ] SEC EDGAR integration for company filings
- [ ] Enhanced visualization dashboard
- [ ] Backtesting framework for recommendation validation
- [ ] Multi-stock portfolio optimization
- [ ] Sector comparison and relative valuation

---

## 👥 Team

**AAI520 - 2025 - Group 18**

- Farhath Bhat
- Varun Jha

---

## 📄 License

This project is created for educational purposes as part of the AAI520 course requirements.

---

## 🙏 Acknowledgments

- **Yahoo Finance** for providing free financial data API
- **yfinance library** developers for the excellent Python wrapper
- Course instructors for project guidance and evaluation criteria

---


## 📚 References

- Yahoo Finance API Documentation
- Agent-based AI System Design Principles
