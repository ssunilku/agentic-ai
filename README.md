

# Coder Buddy 🤖🚀

### Project Overview

It is an autonomous, multi-agent AI software engineer designed to transform natural language instructions into fully functional web applications. Inspired by state-of-the-art generative tools like Lovable and Devin AI, the system automates the entire development lifecycle—from feature planning to final code execution—writing localized codebases straight to your disk.

---

### Key Features

* **Text-to-App Generation:** Outputs ready-to-run frontend applications (such as interactive calculators and to-do lists) from a single prompt.
* **Stateful Agent Workflows:** Uses graph-based execution to maintain a persistent state and control agent behaviors during development.
* **Autonomous File Management:** Features built-in system guardrails that allow the AI to safely write, read, and append logic to specific workspace directories.
* **Automated Project Documentation:** Generates a custom, technical `README.md` for every single application it builds.

---

### Core Architecture & Agent Framework

The system utilizes **LangGraph** to model a collaborative software engineering team. A single shared state dictionary is passed and updated across three dedicated agent nodes:

| Agent Node | Core Responsibility | Output / Artifact |
| --- | --- | --- |
| **Planner Agent** | Analyzes the initial prompt and breaks it down into explicit project scopes and a target file blueprint. | Jira-like user stories and file schemas. |
| **Architect Agent** | Translates the high-level plan into explicit, step-by-step implementation technical guidelines for each file. | Micro-level instruction logs. |
| **Coder Agent** | Operates inside a dynamic **ReAct loop**, deploying file-system tools to iteratively build, read, and refine code files. | Full HTML structure, CSS stylesheets, and JS logic files written to disk. |

---

### Technical Tech Stack

* **Orchestration Engine:** LangGraph & LangChain (State Graph management)
* **LLM Infrastructure:** Groq Cloud API (Utilizing open-source, high-parameter models)
* **Package Management:** UV (Fast Python virtual environment & dependency management)
* **Telemetry & Tracing:** PyCharm AI Agent Debugger & LangChain Globals (`set_debug`)

---

### Installation & Quick Start

> 💡 **Prerequisite:** Ensure you have a free API key generated from the [Groq Cloud Console](https://console.groq.com/).

#### 1. Setup Environment

Install the **UV** package manager and sync dependencies:

```bash
# Install UV (Windows PowerShell)
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"

# Clone & enter repo
git clone https://github.com/your-username/coder-buddy.git
cd coder-buddy

# Seamlessly sync isolated environment and dependencies 
uv sync

```

#### 2. Configure Credentials

Create a `.env` file in the root folder:

```env
GROQ_API_KEY=your_actual_groq_api_key_here

```

#### 3. Execution

Launch the generation pipeline by passing your application concept:

```bash
uv run main.py --prompt "Build a clean, dark-themed calculator web app"

```

*The resulting application files will instantly generate within the `generated_project/` directory.*
