# MultiActor_critique-revise-agents

Developer + Tester agents on a feedback loop: code, test, refine, repeat. One writes. One tests. Together, they ship working code.

# 🧠 Multi-Actor Software Development with LangGraph

This project demonstrates how to build an **agentic software development workflow** using **two GPT-powered agents** — a **Developer Agent** and a **Tester Agent** — who collaboratively build and refine Python code through an automated loop.

## 🚀 What It Does

The system allows AI agents to:
- 🔨 Generate code from a task prompt (Developer Agent)
- 🧪 Write test cases and provide structured feedback (Tester Agent)
- 🔁 Iterate until the code passes all tests or hits a reflection limit

The full loop is orchestrated using [LangGraph](https://github.com/langchain-ai/langgraph), a graph-based framework for building multi-agent systems.

## 🎯 Use Case

You give a task like:
> “Write Python code for the FLAMES game.”

And the system will:
1. Developer Agent writes the first version of the code
2. Tester Agent checks it, runs unit tests, and critiques it
3. Developer revises the code
4. The loop continues until the code is complete or the reflection limit is reached

This demonstrates the **Critique & Revise** design pattern in action.

---

## 🛠 Tech Stack

| Component        | Role                                       |
|------------------|--------------------------------------------|
| Python 3.9+      | Core language                              |
| OpenAI (GPT)     | Developer & Tester agents                  |
| LangChain        | Agent tooling and prompt templates         |
| LangGraph        | Workflow orchestration and state handling  |
| Python REPL Tool | Allows code execution within agent flow    |
| Jupyter Notebook | Development environment (for demos)        |

---

## 📁 File Structure

- `multiactor_softwarebuilding_developer_vs_tester_agents.py`  
   The main Python script with the agent creation, LangGraph definition, and execution loop.

- `run_reflection()`  
   Entry point function to run the loop with any prompt.

- `developer_node()` / `tester_node()`  
   LangGraph nodes implementing each agent’s behavior.

---

## 🧪 Example Tasks

### FLAMES Game:
```python
run_reflection(graph, "Write a python code for the FLAMES game", max_reflections=3)
Tic-Tac-Toe Game:
python
Copy
Edit
run_reflection(graph, "Write a python code for Tic-Tac-Toe", max_reflections=3)
🧠 Key Concepts
Developer Agent: Generates Python code based on prompt + tester feedback.

Tester Agent: Writes unit tests, critiques code, and suggests improvements.

Reflection Loop: Each round improves the output until the tester is satisfied.

StateGraph: Powered by LangGraph, managing all transitions and shared state.

🏁 Getting Started
Install dependencies:

bash
Copy
Edit
pip install langchain langchain-openai langgraph python-dotenv langchain-experimental
Set your OpenAI API key in a .env file:

ini
Copy
Edit
OPENAI_API_KEY=your-key-here
Run the script in a Jupyter Notebook or Python environment.

✨ Highlights
Agent roles are modular and reusable.

Prompt engineering is transparent and configurable.

Visual graph outputs show how the system flows.

Works with any task involving code generation + validation.
