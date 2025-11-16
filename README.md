# Agent Development Kit (ADK)

Google's framework for building sophisticated agentic applications with progressive, step-by-step guidance for developers.

## What is ADK?

The Agent Development Kit (ADK) is Google's comprehensive framework designed to help developers build production-grade agentic applications. It provides structured learning paths and tools to incrementally master agent development capabilities, from basic single-agent systems to complex multi-agent orchestrations.

## Key Features

- **Multi-Agent Systems** - Build and orchestrate teams of collaborative agents with delegation and session management
- **Multi-Tool Integration** - Create workflows that leverage multiple tools to accomplish complex tasks
- **Streaming Capabilities** - Develop agents capable of processing streamed content in real-time
- **LLM and Workflow Agents** - Support for both LLM-powered and workflow-based agent architectures
- **Built-in and Third-Party Tools** - Extensive tool integration options
- **Session Management** - Robust state handling across agent interactions
- **Observability & Evaluation** - Built-in capabilities for monitoring and assessing agent performance
- **Safety & Security** - Comprehensive safety mechanisms and grounding features
- **Cloud Deployment** - Multiple deployment options including Agent Engine, Cloud Run, and GKE

## Supported Languages

The ADK is available in two programming languages:

- **Python** (`adk-python`)
- **Java** (`adk-java`)

## Core concepts
ADK is built around a few key primitives and concepts that make it powerful and flexible. Here are the essentials:

- **Agent**: The fundamental worker unit designed for specific tasks. Agents can use language models (`LlmAgent`) for complex reasoning, or act as deterministic controllers of the execution, which are called "workflow agents" (`SequentialAgent`, `ParallelAgent`, `LoopAgent`).
- **Tool**: Gives agents abilities beyond conversation, letting them interact with external APIs, search information, run code, or call other services.
- **Callbacks**: Custom code snippets you provide to run at specific points in the agent's process, allowing for checks, logging, or behavior modifications.
- **Session Management**: Handles the context of a single conversation (`Session`), including its history (`Events`) and the agent's working memory for that conversation (`State`).
- **Memory**: Enables agents to recall information about a user across multiple sessions, providing long-term context (distinct from short-term session State).
- **Artifact Management** (`Artifact`): Allows agents to save, load, and manage files or binary data (like images, PDFs) associated with a session or user.
- **Code Execution**: The ability for agents (usually via Tools) to generate and execute code to perform complex calculations or actions.
- **Planning**: An advanced capability where agents can break down complex goals into smaller steps and plan how to achieve them like a ReAct planner.
- **Models**: The underlying LLM that powers `LlmAgents`, enabling their reasoning and language understanding abilities.
- **Event**: The basic unit of communication representing things that happen during a session (user message, agent reply, tool use), forming the conversation history.
- **Runner**: The engine that manages the execution flow, orchestrates agent interactions based on Events, and coordinates with backend services.

Note: Features like Multimodal Streaming, Evaluation, Deployment, Debugging, and Trace are also part of the broader ADK ecosystem, supporting real-time interaction and the development lifecycle.

## Core Learning Paths

### 1. Multi-Tool Agents
Learn to create workflows that use multiple tools to accomplish complex tasks, enabling agents to orchestrate various capabilities seamlessly.  
See [multi-tool agent readme](multi_tool_agent/readme_multi_tool_agent.md)

### 2. Agent Teams
Build collaborative multi-agent systems incorporating:
- Agent delegation and coordination
- Session management across agents
- Safety mechanisms and guardrails  
See [agent team readme](agent_team/readme_agent_team.md)



## Getting Started

### Set up environment & Install ADK
```shell
# Create
python -m venv .venv
# Activate (each new terminal)
# macOS/Linux: source .venv/bin/activate
# Windows CMD: .venv\Scripts\activate.bat
# Windows PowerShell: .venv\Scripts\Activate.ps1
```

Activate (xecute in each new terminal session):
macOS / Linux:
```shell
source .venv/bin/activate
```
Windows (Command Prompt):
```shell
.venv\Scripts\activate.bat
```
Windows (PowerShell):
```shell
.venv\Scripts\Activate.ps1
```

### Install Dependencies:
Run the beloww command:
```shell
python3 -m pip  install -r requirements.txt
```

### Configuration: API Keys
Before running any agent step, you must configure your API keys.

Navigate into the directory for the specific step you want to run (e.g., step_1, step_2_anthropic, step_3, etc.).

Each step directory contains a `.env` file. Replace the placeholder values with your actual API keys.

Example .env content:
```shell
# Set to False to use API keys directly (required for multi-model)
GOOGLE_GENAI_USE_VERTEXAI=FALSE

# --- Replace with your actual keys ---
GOOGLE_API_KEY=PASTE_YOUR_ACTUAL_GOOGLE_API_KEY_HERE
ANTHROPIC_API_KEY=PASTE_YOUR_ACTUAL_ANTHROPIC_API_KEY_HERE
OPENAI_API_KEY=PASTE_YOUR_ACTUAL_OPENAI_API_KEY_HERE
# --- End of keys ---
```



## Agents
In the Agent Development Kit (ADK), an **Agent** is a self-contained execution unit designed to act autonomously to achieve specific goals. Agents can perform tasks, interact with users, utilize external tools, and coordinate with other agents.

The foundation for all agents in ADK is the BaseAgent class. It serves as the fundamental blueprint. To create functional agents, you typically extend BaseAgent in one of three main ways, catering to different needs – from intelligent reasoning to structured process control.
![agent types](images/agent-types.png)

### Core Agent Categories
ADK provides distinct agent categories to build sophisticated applications:

1. [LLM Agents (LlmAgent, Agent)](agents/llm_agents.md): These agents utilize **LLMs** (Large Language Models) as their core engine to understand natural language, reason, plan, generate responses, and **dynamically decide** how to proceed or which tools to use, making them ideal for flexible, language-centric tasks. 

2. [Workflow Agents (SequentialAgent, ParallelAgent, LoopAgent)](agents/workflow_agents.md): These specialized agents control the execution flow of other agents in predefined, **deterministic patterns** (sequence, parallel, or loop) without using an LLM for the flow control itself, perfect for structured processes needing predictable execution. 

3. [Custom Agents](agents/custom_agents.md): Created by extending BaseAgent directly, these agents allow you to implement unique operational logic, specific control flows, or specialized integrations not covered by the standard types, catering to highly tailored application requirements. 


### Choosing the Right Agent Type
The following table provides a high-level comparison to help distinguish between the agent types. As you explore each type in more detail in the subsequent sections, these distinctions will become clearer.

| Feature |	LLM Agent (`LlmAgent`) |	Workflow Agent (`SequentialAgent`, `ParallelAgent`, `LoopAgent`) |	Custom Agent (`BaseAgent` subclass) |
|---|---|---|---|
| **Primary Function** |	Reasoning, Generation, Tool Use |	Controlling Agent Execution Flow |	Implementing Unique Logic/Integrations |
| **Core Engine** |	Large Language Model (LLM) |	Predefined Logic (Sequence, Parallel, Loop) |	Custom Code |
| **Determinism** |	Non-deterministic (Flexible) |	Deterministic (Predictable) |	Can be either, based on implementation** |
| **Primary Use** |	Language tasks, Dynamic decisions |	Structured processes, Orchestration |	Tailored requirements, Specific workflows |

### Agents Working Together: Multi-Agent Systems
While each agent type serves a distinct purpose, the true power often comes from combining them. Complex applications frequently employ multi-agent architectures where:

- **LLM Agents** handle intelligent, language-based task execution.
- **Workflow Agents** manage the overall process flow using standard patterns.
- **Custom Agents provide specialized capabilities or rules needed for unique integrations.
Understanding these core types is the first step toward building sophisticated, capable AI applications with ADK.

## Resources

- [Official Documentation](https://google.github.io/adk-docs/)
- [Tutorials](https://google.github.io/adk-docs/tutorials/)

