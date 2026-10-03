# LangChain + AI Agent Notebook

This repository contains a Jupyter notebook demonstrating how to use LangChain with Groq models to build and experiment with AI agents and tool-calling workflows.

## Notebook

- `langchain+agent.ipynb`

## What this notebook covers

The notebook walks through the following concepts:

- Installing the required packages
- Setting up a Groq API key
- Creating a `ChatGroq` model
- Sending basic prompts to an LLM
- Building a simple prompt chain
- Defining custom tools using `@tool`
- Binding tools to an LLM
- Calling tools from the model
- Creating an agent with `create_agent()`
- Using conversation memory as part of agent interactions
- Defining a system prompt for agent behavior
- Using structured output with Pydantic models

## Technologies used

- Python
- LangChain
- LangChain Groq integration
- Groq models
- Pydantic
- Jupyter Notebook

## Setup

Before running the notebook, make sure you have:

- Python 3.9+ installed
- A Groq API key
- Access to Jupyter or Google Colab

Install the required libraries:

```bash
pip install -U langchain langchain-groq
```

Then set your Groq API key in the notebook:

```python
import os
from langchain_groq import ChatGroq

os.environ["GROQ_API_KEY"] = input("Enter your groq api key:")
```

## Example workflow in the notebook

The notebook creates a model like this:

```python
llm = ChatGroq(
    model="openai/gpt-oss-120b",
    temperature=0
)
```

It also defines a simple tool:

```python
from langchain_core.tools import tool

@tool
def add_numbers(a: int, b: int) -> int:
    """add two numbers."""
    return a + b
```

Then it binds the tool to the model and creates an agent for simple arithmetic and reasoning tasks.

## Learning goals

This notebook is useful for learning:

- how to connect LangChain to Groq
- how chat models work in Python
- how prompt templates are used
- how tool calling works in LLM applications
- how agents can decide when to use available tools
- how to build simple AI workflows with structured responses

## Notes

This project is a beginner-friendly notebook focused on experimentation and learning rather than a production-ready application. It is ideal for trying out LangChain agent patterns in a quick, interactive environment.

## Run it

Open the notebook in:

- Jupyter Notebook
- JupyterLab
- Google Colab

Then run each cell in order.

## License

This repository does not currently include a formal license file. If you plan to share or reuse it publicly, consider adding one.
