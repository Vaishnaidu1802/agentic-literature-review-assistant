\# Agentic Literature Review Assistant

An agentic AI system that automates academic literature reviews by retrieving, analyzing, summarizing, evaluating, and iteratively refining research findings.

It combines hybrid retrieval, multi-agent orchestration, self-reflection, reinforcement learning, tool integration, and human-in-the-loop mechanisms.

\#\# Overview

Traditional literature review systems typically follow:

Query → Retrieve → Generate

This project extends that into an agentic workflow capable of planning, evaluating its own output, reflecting on weaknesses, and refining its search strategy across multiple iterations.

\#\# System Architecture

Research Query    
↓    
Query Validation    
↓    
Planner Agent    
↓    
Query Decomposition    
↓    
Hybrid Retrieval    
↓    
BM25 \+ FAISS    
↓    
Summarizer Agent    
↓    
Evaluator Agent    
↓    
Self-Reflection    
↓    
Query Refinement    
↓    
Final Literature Review

If quality thresholds are not satisfied, the agent refines the query and repeats the retrieval process.

\#\# Key Features

\#\#\# Multi-Agent Architecture

\- Planner Agent – decomposes research questions into focused sub-queries  
\- Retriever Agent – searches and ranks relevant academic papers  
\- Summarizer Agent – extracts and synthesizes findings  
\- Evaluator Agent – evaluates generated research summaries  
\- Orchestrator Agent – coordinates the complete workflow

\#\#\# Hybrid Retrieval

The system combines:

\- BM25 sparse retrieval  
\- FAISS dense retrieval  
\- Sentence Transformer embeddings using \`all-MiniLM-L6-v2\`

Normalized scores are combined using:

\- BM25 weight: 0.6  
\- FAISS weight: 0.4

\#\#\# Agentic Reasoning

The system follows a ReAct-inspired cycle:

Thought → Action → Observation

Agents perform actions such as retrieval, summarization, evaluation, query refinement, and task completion.

\#\#\# Self-Reflection

After each iteration, the system evaluates the generated literature review. If quality thresholds are not satisfied, the Reflection module identifies weaknesses and improves the research query.

A maximum of three refinement iterations is performed.

\#\#\# MCP-Style Tool Registry

Available tools include:

\- \`fetch\_papers\`  
\- \`bm25\_search\`  
\- \`faiss\_search\`  
\- \`summarize\`  
\- \`evaluate\_relevance\`

\#\#\# Reinforcement Learning

The project explores query optimization using:

\- PPO  
\- DPO  
\- GRPO

\#\#\# Human-in-the-Loop

\- Confidence \> 0.50 → automatic approval  
\- Confidence 0.35–0.50 → human review  
\- Confidence \< 0.35 → domain expert escalation

\#\#\# Security Layer

Tool requests are checked for:

\- Prompt injection  
\- Tool misuse  
\- Malicious input patterns  
\- Goal-alignment issues

\#\# Evaluation Framework

The system evaluates:

\- Perception  
\- Reasoning  
\- Tool Usage  
\- Coherence  
\- Grounding  
\- Hallucination Risk

\#\# Results

The system was evaluated on 149 academic papers from Semantic Scholar and arXiv.

| Metric | Result |  
|---|---:|  
| Papers Retrieved | 149 |  
| Initial Overall Score | 0.8197 |  
| Final Overall Score | 0.8356 |  
| Reasoning Score | 1.0 |  
| Grounding Score | 1.0 |  
| Hallucination Risk | 0.0 |

PPO and DPO experiments achieved a maximum score of 0.8507.

\#\# Technology Stack

\- Python  
\- FAISS  
\- BM25 / rank-bm25  
\- Sentence Transformers  
\- all-MiniLM-L6-v2  
\- NumPy  
\- Pandas  
\- scikit-learn  
\- Matplotlib  
\- Semantic Scholar API  
\- arXiv API  
\- Jupyter Notebook / Google Colab  
