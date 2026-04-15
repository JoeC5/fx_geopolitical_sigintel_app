# Forex Geopolitical Signal Intelligence App

An AI-powered Streamlit application that analyzes how geopolitical events and macroeconomic data impact foreign exchange (FX) markets.
The system combines real-time intelligence, structured economic data, and multi-model AI reasoning to generate concise, actionable FX briefings for traders, analysts, and risk managers.

## Why This Matters

FX markets react rapidly to geopolitical events, central bank actions, and macroeconomic shifts. However, relevant insights are often fragmented across:
- News sources
- Economic datasets
- Analyst reports 
This application consolidates these inputs into a single, AI-generated intelligence briefing, enabling faster, more informed decision-making.

## Overview
This application allows users to input a geopolitical or macroeconomic event (e.g., Fed rate decision, geopolitical conflict, election) and generates a structured report covering:

FX Impact
- USD/GBP
- USD/EUR
- GBP/EUR

Supporting Signals
- Geopolitical developments
- Central bank activity
- Economic indicators
- Trade and sanctions
- Political stability
  
AI-Generated Outputs
- Executive summary
- Signal analysis
- Economic context
- FX outlook (30–90 days)
- Recommended actions 
<img src="assets/fx sigintel app- screenshots.png" alt="FX SigIntel App Screenshot" width="800"/>

## Sample Output
A full example of the generated report is available in the repository:
[View Sample Report: Iranian War Scenario](assets/fx_sigint_Iranian_War_20260414_.docx)

Disclaimer: This tool provides informational and analytical insights only and does not constitute financial advice or investment recommendations.

## Architecture
The application follows a multi-agent pipeline design, where each component has a distinct role.

### 1. Data Layer
   
- Federal Reserve Economic Data
  -  CPI (Inflation) 
  -  GDP Growth 
  -  Interest Rates 
  -  Employment / NFP 
- Live FX rates (Open Exchange Rate API)

### 2. Research Agent — OpenAI GPT-4.1

- Uses web_search_preview for real-time intelligence 
- Dynamically generates search queries based on: 
  -  Event 
  -  Signal category 
  -  Time window 
- Outputs: 
  -  Structured bullet-point findings 
  -  Source attribution

### 3. Synthesis Agent — Claude

- Uses Claude Sonnet for long-form reasoning and synthesis 
- Combines: 
  -  Web research findings 
  -  Macroeconomic data 
  -  Historical FX context 
- Produces: 
  -  Full FX intelligence briefing (~650–900 words) 
  -  Structured, analyst-style output
    
### 4. UI Layer — Streamlit

- Interactive inputs: 
  -  Event/topic 
  -  Lookback window 
  -  Region focus 
  -  Signal categories 
- Outputs: 
  -  Live FX rates 
  - Pipeline logs 
  -  AI-generated briefing 
  - Downloadable reports (.docx, .md) 

## Features

### Intelligent Research
- Multi-query web search per signal category
- Source duplication and attribution
  
### Economic Context Integration
- Real-time macroeconomic data (US, UK, EU)
- Cross-country comparison
  
### AI Reasoning
- Context-aware synthesis using historical precedents 
- Signal prioritization: 
- Risk 
- Watch 
- Opportunity 

### Exportable Reports
- Word document (.docx) 
- Markdown (.md)
   
### Real-Time Insights
- Live FX rate display 
- TradingView chart links 

## Example Workflow

### User Input:
- "Fed rate hike expectations"
  
### System Process:
- Pulls CPI, GDP, rates, and employment data
- Retrieves latest geopolitical and market developments 
- Synthesizes insights using AI agents
  
### Output:
- USD strengthening bias vs EUR/GBP
- Hawkish Fed signals + inflation persistence
- Risk classification: Opportunity (USD long bias)
- Downloadable FX intelligence briefing 

## AI-Assisted Development

This project was developed using a multi-model AI-assisted workflow:
- OpenAI GPT-4.1 → research agent design and Implementation 
- Claude → code development support, refinement, and structured reasoning logic
  
All system architecture, orchestration, and application design were defined with a focus on building a production-style multi-agent pipeline.

The approach treats AI models as modular components within a larger system, rather than standalone tools.

## Installation

### 1. Clone the repository
git clone https://github.com/yourusername/forex-signal-intelligence.git
cd forex-signal-intelligence

### 2. Install dependencies
pip install -r requirements.txt

### 3. Set up environment variables
Create a .env file:
- OPENAI_API_KEY=your_openai_api_key
- ANTHROPIC_API_KEY=your_anthropic_api_key
- FRED_API_KEY=your_fred_api_key
  
Get a free FRED API key:
https://fred.stlouisfed.org/docs/api/api_key.html

### 4. Run the app
streamlit run app.py

## Configuration

### Lookback Windows
- 1 day → 6 months
  
### Signal Categories
- Geopolitical Events 
- Central Bank / Rates 
- Trade & Sanctions 
- Military / Security 
- Political Stability 
- Economic Releases
  
### Region Focus
- UK / Europe 
- US / UK 
- US / Europe 
- Global 

## Future Enhancements
- **Signal Backtesting Engine**
  Evaluate predictive accuracy of generated FX signals against historical market movements  

- **Event Sentiment Scoring (NLP)**  
  Quantify geopolitical sentiment to enhance signal prioritization  

- **Time-Series Analytics Dashboard**  
  Visualize FX trends, signal evolution, and macroeconomic indicators  

## Author
This project demonstrates the design and implementation of a multi-agent AI system for financial intelligence.
It reflects a focus on combining AI, data, and automation to build practical, decision-support tools.

## License
- MIT License 


