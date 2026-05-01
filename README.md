# Agentic-Code-Healer
RAG 长链召回、Actor-Critic 多 Agent 辩论 和 反思闭环
# Agentic-Code-Healer 🛡️

A Multi-Agent driven Automated Code Audit and Self-Healing System designed for large-scale microservice architectures.

## Overview
Agentic-Code-Healer leverages Long-Context Large Language Models and a Multi-Agent collaboration framework to automate Code Review (CR), technical debt remediation, and rapid bug fixing. By utilizing RAG (Retrieval-Augmented Generation) across entire codebases and an Actor-Critic agent debate mechanism, it ensures robust, secure, and highly optimized code generation.

## Core Architecture 🧠

1. **Context-Retriever (RAG):** Extracts deep dependency chains and architectural context from multi-repo setups (Often consuming 100k+ tokens per PR).
2. **Coder Agent:** Generates initial structural fixes and refactoring PRs based on the global context.
3. **Reviewer Agent:** Acts as a Senior Architect/Security Expert. Engages in multi-turn debate (Actor-Critic) with the Coder Agent until performance and security standards are met.
4. **Tester Agent (Self-Reflection):** Generates boundary test cases. If tests fail, the error stack trace is fed back into the Coder for self-correction.

## Token Consumption Warning ⚠️
**High Token Usage:** Due to the requirement of injecting full architectural context (Long Context Window) and the multi-turn debate loops between agents, this system consumes an average of **50k - 200k tokens per complex PR analysis**. Daily enterprise-scale operations run into the tens of millions of tokens.

## Setup
```bash
pip install -r requirements.txt
export LLM_API_KEY="your_api_key_here"
---

### 2. `requirements.txt` (依赖文件，增加真实感)

```text
langchain>=0.1.0
pydantic>=2.5.0
chromadb>=0.4.20
openai>=1.10.0
tiktoken>=0.5.2
pytest>=8.0.0
