# AI Helpers

## Overview
This repository contains code utilizing LLMs for advanced RAG applications (Agents, ReAct, CRAG...) over written text, video, and audio. The individual notebooks extensively utilize the OpenAI API and the LangChain library. In addition, LangSmith is used for evaluation.

## Corrective RAG (CRAG) implemented with LangGraph
- <span style="font-size:larger;">**Corrective RAG**</span>: Implementation of the advanced Corrective RAG technique based on this paper: [Corrective Retrieval Augmented Generation](https://arxiv.org/abs/2401.15884).
    - The user query is used for regular RAG.
    - LLM evaluates the retrieved documents for relevance.
    - If at least one document is found not relevant, a transformed query is used for web search.
    - Finally, RAG and web search results are used for answer generation.
- <span style="font-size:larger;">**LangGraph**</span>: The flow of the CRAG logic is implemented using LangGraph.
- <span style="font-size:larger;">**LangSmith**</span>: The code is traced with LangSmith for evaluation.

## ReAct Agent
- <span style="font-size:larger;">**Tool use**</span>: Search with Wikipedia API, Tavily Search, perform RAG over a given PDF, perform RAG over a given YouTube link.
- <span style="font-size:larger;">**PDF Processing**</span>: Load, chunk, and index PDF documents using Chroma DB vector store.
- <span style="font-size:larger;">**YouTube Video Processing**</span>: Download YouTube videos, generate transcripts via LLM, and chunk and index for RAG.
- <span style="font-size:larger;">**Information Retrieval**</span>: Vector stores retrieval using Maximal Marginal Relevance (MMR).
- <span style="font-size:larger;">**Chat memory**</span>: Advanced chat memory with implicit copy of the messages until a variable buffer size is reached, after that a summary is created by the LLM.

## RAG chat bot with memory
- <span style="font-size:larger;">**PDF Processing**</span>: Load, chunk, and index PDF documents using Chroma DB vector store.
- <span style="font-size:larger;">**Information Retrieval**</span>: Vector stores retrieval using Maximal Marginal Relevance (MMR).
- <span style="font-size:larger;">**Chat memory**</span>: Memory is simply adding the chat messages until reset.
