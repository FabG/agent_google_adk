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

## Core Learning Paths

### 1. Multi-Tool Agents
Learn to create workflows that use multiple tools to accomplish complex tasks, enabling agents to orchestrate various capabilities seamlessly.
See [multi-tool agent readme](multi_tool_agent/multi_tool_agent_readme.md)

### 2. Agent Teams
Build collaborative multi-agent systems incorporating:
- Agent delegation and coordination
- Session management across agents
- Safety mechanisms and guardrails

### 3. Streaming Agents
Develop agents capable of processing and responding to streamed content in real-time, ideal for interactive applications.

### 4. Sample Applications
Explore reference implementations across various domains:
- Retail applications
- Travel and booking systems
- Customer service bots
- And more

## Getting Started

Set up environment & Install ADK
```shell
# Create
python -m venv .venv
# Activate (each new terminal)
# macOS/Linux: source .venv/bin/activate
# Windows CMD: .venv\Scripts\activate.bat
# Windows PowerShell: .venv\Scripts\Activate.ps1
```

Install ADK:
```shell
python3 -m pip install google-adk
```



## Resources

- [Official Documentation](https://google.github.io/adk-docs/)
- [Tutorials](https://google.github.io/adk-docs/tutorials/)

