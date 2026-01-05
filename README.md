# IITM-Hacktahon-

# The Autonomous Financial Analyst
Agentic orchestration platform designed to modernize the financial reporting lifecycle. Unlike "Chat with PDF" wrappers that hallucinate numbers, FinAgent uses a Multi-Agent System (MAS) to parse complex banking logs, perform deterministic SQL reconciliation, and forecast cash flow trends—all without sensitive data leaving your infrastructure.

## Problem Statement
Financial institutions rely on legacy reporting formats—static PDF Settlement Reports, CSV Authorization Logs, and mainframe Fixed-Width Clearing Files (e.g., Visa TC33).

* Reactive & Manual: Analysts spend hours manually cross-referencing thousands of rows in Excel.

* Static Data: Insights are trapped in "dead" documents that cannot be queried.

* High Error Rate: Manual reconciliation often misses subtle discrepancies or fee anomalies.

## The Solution
Agent acts as an autonomous financial analyst. It transforms static reports into a dynamic, queryable intelligence layer.

* Ingests diverse formats (PDF tables, Mainframe logs) into a live SQL database.

* Reconciles transactions deterministically using SQL (zero-error math).

* Explains complex banking rules using Semantic Search (RAG).

* Forecasts liquidity needs using local Machine Learning models.

## System Architecture
Agent utilizes a "Split-Brain" Memory Architecture to decouple reasoning from calculation, ensuring accuracy and scalability.

<img width="1600" height="872" alt="image" src="https://github.com/user-attachments/assets/370e1d1a-75b1-4c61-9581-14ee906980d2" />

Layers :

1. Ingestion Layer: "Fidelity-First" parsers (Marker, Pandas) preserve table structures from PDFs and decode fixed-width legacy files.

2. Memory Layer:

* Analytical (DuckDB): Stores transaction rows for exact math.

* Semantic (ChromaDB): Stores compliance rules and error codes.

* Short-Term (SQLite): Maintains chat session context.

3. Orchestration Layer: LangGraph manages the cyclic workflow, allowing agents to plan, execute, and self-correct.

4. Guardrails: A Relevance Classifier ensures only valid financial documents are processed.

## Key Features
1. Multi-Format Intelligent Ingestion
Seamlessly handles Authorization Logs (CSV), Clearing Files (Fixed-Width), and Settlement Reports (PDF) simultaneously. Uses Deep Learning OCR to preserve table integrity.

2. Deterministic Reconciliation Engine
We do not ask the LLM to do math. The agent writes SQL queries that are executed by DuckDB, instantly identifying discrepancies (e.g., "5 transactions missing totaling $450") with 100% precision.

3. Contextual RAG & Explanation
Decodes obscure banking error codes (e.g., "Code 51") by retrieving definitions from the uploaded Compliance Guides (stored in ChromaDB) and explaining them in plain English.

4. Automated Forecasting
Integrated Python REPL allows the agent to run Linear Regression on historical settlement data to predict future cash flow requirements.

5. Privacy-First Deployment
Designed to run entirely on-premise or in a private cloud container. Sensitive financial data never touches public API endpoints.
