# 🔗 LangChain For Beginners
Welcome to **LangChain For Beginners** course!

This repository is the companion to the YouTube playlist located [here](TBA).

## Table of Contents
- [📚 Course](#-course)
  - [Module 1: Intro to Agents](#module-1-intro-to-agents)
- [🚀 Setup](#-setup)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Run Notebooks More Info](#run-notebooks-more-info)
- [📖 Related Resources](#-related-resources)
  - [Python Virtual Environments](#python-virtual-environments)
  - [Model Providers](#model-providers)
  - [Environment Variables](#environment-variables)
  - [Development Environment](#development-environment)
- [Acknowledgements](#acknowledgements)

## 📚 Course

### Module 1: Intro to Agents

| Video                                                                          |                                                                                                              Notebook                                                                                                               |
|:-------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| [**1. Intro To LangChain & How To Setup It Up**](https://youtu.be/vDs9qShpV40) |                                                    [1.01](https://github.com/discrete-horizon/langchain-for-beginners/blob/main/notebooks/module-01-intro/1.01-first-chat.ipynb)                                                    |
| [**2. Create An Agent In LangChain**](https://youtu.be/WlcRFQWlhd0)            |                                                [1.02](https://github.com/discrete-horizon/langchain-for-beginners/blob/main/notebooks/module-01-intro/1.02-creating-an-agent.ipynb)                                                 |
| [**3. Basic Prompting And Structured Output**](https://youtu.be/ywuChfLEZuM)   |                                         [1.03](https://github.com/discrete-horizon/langchain-for-beginners/blob/main/notebooks/module-01-intro/1.03-prompting-and-structured-output.ipynb)                                          |
| [**4. What Are Tools?**](https://youtu.be/zlcirVQIxRA)                         |                                                      [1.04](https://github.com/discrete-horizon/langchain-for-beginners/blob/main/notebooks/module-01-intro/1.04-tools.ipynb)                                                       |
 | [**5. How to Add Memory To Your Agents?**](https://youtu.be/mquu8VJMVJ4)       | [1.05](https://github.com/discrete-horizon/langchain-for-beginners/blob/main/notebooks/module-01-intro/1.05-memory.ipynb)

[//]: # (- Intro & Setup)

[//]: # (- Creating an Agent)

[//]: # (- Basic Prompting)

[//]: # (- Tools)

[//]: # (- Short-Term Memory)

[//]: # (- Multimodal Messages)

[//]: # (- Project: TBA)

## 🚀 Setup

### Prerequisites

- The [Chrome](https://www.google.com/chrome/) browser is recommended
- [git](https://git-scm.com/install/) is recommended
- A package/project manager: [uv](https://docs.astral.sh/uv/) (recommended) or [pip](https://pypi.org/project/pip/)
- The course requires Python >=3.12, <3.14  If you use `uv`, it will take care of this for you. [More info](#python-virtual-environments)


### Installation

Download the course repository
```bash
# Clone the repo
git clone --depth 1 https://github.com/discrete-horizon/langchain-for-beginners
cd langchain-for-beginners
```

Make a copy of example.env
```bash
# Create .env file
cp example.env .env
```

Edit the .env file to include the keys below for [Models](#model-providers) and optionally [LangSmith](#getting-started-with-langsmith)

- Get an OpenAI API Key [here](https://openai.com/index/openai-api/).  
- Optional for Module1/Lesson1, get an Anthropic API Key [here](https://console.anthropic.com) and a Google API Key [here](https://ai.google.dev/gemini-api/docs/quickstart).
- Optional, Create a [LangSmith](https://smith.langchain.com/) account and API Key.  

```bash
# Third party keys (only one of them is required)
OPENAI_API_KEY = 'your_openai_api_key_here'
ANTHROPIC_API_KEY = 'your_anthropic_api_key_here'
GOOGLE_API_KEY = 'your_google_api_key_here'
TAVILY_API_KEY = 'your_tavily_api_key_here'

# Langsmith keys (Optional for evaluation and tracing)
LANGSMITH_API_KEY = 'your_langsmith_api_key_here'
# uncomment to set tracing to true when you set up your LangSmith account
# LANGSMITH_TRACING=true
LANGSMITH_ENDPOINT=https://api.smith.langchain.com
# Uncomment the following if you are on the EU instance:
#LANGSMITH_ENDPOINT=https://eu.api.smith.langchain.com
LANGSMITH_PROJECT=dh-langchain-for-beginners
```


Make a virtual environment and install dependencies. [More info](#python-virtual-environments)

<details open>
<summary>Using uv (recommended)</summary>

```bash
uv sync
```

</details>

<details>
<summary>Using pip</summary>

```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

</details>


### Run Notebooks [More Info](#development-environment)

<details open>
<summary>Using uv (recommended)</summary>

```bash
uv run jupyter lab
```

</details>

<details>
<summary>Using pip</summary>

```bash
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
jupyter lab
```

</details>



## 📖 Related Resources

### Python Virtual Environments

Managing your Python version is often best done with virtual environments. This allows you to select a Python version for the course independent of the system Python version.

<details open>
<summary>Using uv (recommended)</summary>

`uv` will install a version of Python compatible with the versions specified in the `pyproject.toml` in the `.venv` directory when running the `uv sync` specified above. It will use this version when invoking with `uv run`. For additional information, please see [uv](https://docs.astral.sh/uv/).
</details>

<details>
<summary>Using pyenv + pip</summary>

If you are using pip instead of uv, you may prefer using pyenv to manage your Python versions. For additional information, please see [pyenv](https://github.com/pyenv/pyenv).

```bash
pyenv install 3.12
pyenv local 3.12
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

</details>

### Model Providers

If you don't have an OpenAI API key, you can sign up [here](https://openai.com/index/openai-api/). The course primarily uses gpt-5-nano which is very inexpensive.  If desired, you may also obtain additional API keys for [Anthropic](https://console.anthropic.com) or [Google](https://ai.google.dev/gemini-api/docs/quickstart).

This course has been created using particular models and model providers.  You can use other providers, but you will need to update the API keys in the .env file and make some necessary code changes. LangChain supports many chat model providers. [More Info](https://docs.langchain.com/oss/python/integrations/providers/all_providers).

Tavily is a search provider that returns search results in an LLM-friendly way. They have a generous free tier. [Tavily](https://tavily.com)

### Environment Variables

This course uses the [dotenv](https://pypi.org/project/python-dotenv) module to read key-value pairs from the .env file and set them in the environment in the Jupyter notebooks. They do not need to be set globally in your system environment.


### Development Environment

The course uses [Jupyter](https://jupyter.org/) notebooks. The Jupyter package is installed in the virtual environment and can be run as described above. Jupyter notebooks can also be edited and run in your desired IDE like VSCode, PyCharm or Cursor.


## Acknowledgements

I need to credit the great work of [LangChain Academy](https://academy.langchain.com/), specifically the [lca-lc-foundations](https://github.com/langchain-ai/lca-lc-foundations) course. In many parts I have learned from them. Please have a look at their courses for some in-depth tutorials.
