# Workflow Agents

Workflow agents are specialized components in ADK designed purely for **orchestrating the execution flow of sub-agents**. Their primary role is to manage how and when other agents run, defining the control flow of a process.

Unlike [LLM Agents](llm_agents.md), which use Large Language Models for dynamic reasoning and decision-making, Workflow Agents operate based on **predefined logic**.  

They determine the execution sequence according to their type (e.g., sequential, parallel, loop) without consulting an LLM for the orchestration itself. This results in **deterministic and predictable execution patterns**.

ADK provides three core workflow agent types, each implementing a distinct execution pattern:
- [Sequential Agents](workflow_agents/sequential-agents.md)
- [Loop Agents](workflow_agents/loop-agents.md)
- [Parallel Agents](workflow_agents/parallel-agents.md)

Go back to parent readme [here](../README.md)