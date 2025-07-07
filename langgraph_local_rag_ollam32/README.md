# langgraph_local_rag_ollam32

This repo contiains the code for a local RAG setup using:
- LangGraph framework for LLM development
- Ollama + Llama 3.2 for local LLM inference

## Pre-requisites before running

1. Run `uv sync`
2. Install Ollama from https://ollama.com/
3. Run the following command to download llama3.2 `ollama pull llama3.2:3b-instruct-fp16`

## References used
- Code & main logic https://langchain-ai.github.io/langgraph/tutorials/rag/langgraph_adaptive_rag_local/