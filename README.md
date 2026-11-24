# Learning Agentic AI — LangGraph Fundamentals

A small collection of Jupyter notebooks exploring foundational workflow patterns with **LangGraph** and **LangChain**. The repository is a learning workspace, not a packaged autonomous-agent application.

## Notebooks

| Notebook | What it explores |
|---|---|
| `simple_llm_workflow.ipynb` | A single-node LangGraph workflow that sends a question to a Groq chat model and returns an answer |
| `promptChaining.ipynb` | A sequential outline-generation → blog-generation workflow using a Groq model |
| `bmi_workflow.ipynb` | A state-based workflow that calculates BMI and assigns a category; this example does not call an LLM |
| `test.ipynb` | Empty notebook placeholder at the time of this README update |

## Concepts covered

- `StateGraph`, nodes, edges, and shared workflow state
- Sequential prompt chaining
- Calling chat models from workflow nodes
- Separating deterministic Python steps from LLM-powered steps

## Requirements

Python 3.10+ is recommended.

```bash
python -m venv .venv

# Windows PowerShell
.venv\Scripts\Activate.ps1

# macOS / Linux
source .venv/bin/activate

pip install langgraph langchain-groq python-dotenv jupyter
```

Start Jupyter:

```bash
jupyter lab
```

## Model configuration

The LLM notebooks use `ChatGroq` and configure `openai/gpt-oss-120b`. Set your Groq key in the environment before running those notebooks:

```dotenv
GROQ_API_KEY=your_groq_api_key
```

Keep `.env` out of Git. The BMI workflow can be run without a model key.

## Current scope

These notebooks demonstrate basic graph construction and chaining. They do not yet implement a complete tool-using agent, persistent memory, production error handling, or a deployed API. Review the graph wiring in each notebook before relying on it as a reusable workflow.
