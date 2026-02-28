# AI Colab

A collection of Google Colab notebooks exploring AI frameworks — **LangChain** and **LangGraph** — powered by Google's Generative AI (Gemini).

## Notebooks

### 1. [`langchain.ipynb`](langchain.ipynb)
Demonstrates how to use **LangChain** with Google Generative AI to build LLM-powered applications.

- Installs `langchain-google-genai` and `python-dotenv`
- Connects to a Gemini model via LangChain's `ChatGoogleGenerativeAI`
- Shows how to invoke the model with a prompt and parse the response

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sujithkumarmp/ai-colab/blob/main/langchain.ipynb)

---

### 2. [`langgraph.ipynb`](langgraph.ipynb)
Demonstrates how to build an **agentic workflow** using **LangGraph** with tool calling.

- Defines custom tools (e.g., an `add` arithmetic tool)
- Binds tools to a Gemini model
- Builds a LangGraph `StateGraph` with a tool-calling agent loop
- Visualizes the graph and streams a multi-step conversation

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sujithkumarmp/ai-colab/blob/main/langgraph.ipynb)

---

## Prerequisites

- A **Google account** to run notebooks on [Google Colab](https://colab.research.google.com/)
- A **Google AI API key** (obtainable from [Google AI Studio](https://aistudio.google.com/))

## Getting Started

1. Click the **Open In Colab** badge next to the notebook you want to run.
2. When prompted, enter your Google AI API key (stored securely as a Colab secret or via `python-dotenv`).
3. Run all cells in order.

## Dependencies

| Package | Purpose |
|---|---|
| `langchain-google-genai` | LangChain integration for Google Generative AI |
| `langgraph` | Framework for building stateful, multi-step AI agents |
| `python-dotenv` | Load environment variables (API keys) from a `.env` file |
