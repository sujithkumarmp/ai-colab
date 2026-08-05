# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository overview

This repo is a small collection of **Google Colab notebooks** (not a Python package/application) that demonstrate how to build LLM-powered agents with **LangChain** and **LangGraph**, using Google's Gemini models via `langchain-google-genai`. There is no build system, package manifest, lint config, or test suite — the notebooks are the deliverable.

- `langchain.ipynb` — walks through core LangChain concepts in sequence: chat model init (`init_chat_model` / `ChatGoogleGenerativeAI`), messages (`SystemMessage`/`HumanMessage`/`AIMessage`), tool definition with `@tool`, agent creation via `langchain.agents.create_agent`, dependency injection with `context_schema` dataclasses, short-term memory via `langgraph.checkpoint.memory.InMemorySaver` (thread-scoped conversations), and the three LangGraph streaming modes (`values`, `messages`, `custom`).
- `langgraph.ipynb` — builds an agentic tool-calling loop directly with LangGraph's `StateGraph` primitives: defines a custom tool (e.g. `add`), binds tools to a Gemini model, wires a graph with conditional routing between the LLM node and a tool node, visualizes the graph, and streams a multi-step conversation.

Each notebook is self-contained and structured as a linear tutorial (markdown explanation cells interleaved with runnable code cells) — read cells top-to-bottom to understand a notebook rather than jumping to a single cell in isolation.

## Working with the notebooks

There are no build/lint/test commands in this repo. To run or edit a notebook:

- Preferred: open it in Google Colab via the "Open In Colab" badge linked from `README.md`, or directly at `https://colab.research.google.com/github/sujithkumarmp/ai-colab/blob/main/<notebook>.ipynb`.
- Locally: `jupyter notebook langchain.ipynb` (or `langgraph.ipynb`), after installing the packages the notebook itself `%pip install`s in its setup cells (`langchain`, `langchain-google-genai`, `langgraph`, `python-dotenv`, etc.).

Both notebooks require a Google AI API key (from Google AI Studio). In Colab this is read via `google.colab.userdata`; locally it's expected via `python-dotenv`/environment variables. Never hardcode API keys into notebook cells.

When editing a notebook, keep changes scoped to individual cells and preserve the tutorial's incremental structure — later cells often depend on names/imports defined in earlier cells within the same notebook.
