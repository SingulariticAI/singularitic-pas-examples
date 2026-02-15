# singularitic-pas-examples
Quickstart code examples showing how to integrate Singularitic PAS (Pre-Execution Authorization System) with popular agent frameworks: LangChain, CrewAI, AutoGen, LlamaIndex, Haystack, Semantic Kernel, and more.

# Singularitic PAS Examples

Quickstart code examples showing how to integrate **Singularitic PAS** (Pre-Execution Authorization System)  
into the most popular agent orchestration frameworks.

PAS enforces **No Permission → No Execution** — every proposed action is intercepted, evaluated against your policies,  
and only proceeds if cryptographically sealed and attested.

## Why PAS?

- Cryptographic pre-execution gates (Ed25519 seals + one-time tokens)
- Supports single-sig (auto <5 ms) and multi-sig / human review flows
- Immutable audit trail + structured deny reasons
- Works with existing agent loops — no full rewrite required

## Supported Frameworks (so far)

| Framework       | Folder                  | Description                                      | Status     |
|-----------------|-------------------------|--------------------------------------------------|------------|
| LangChain       | /langchain              | BaseTool wrapper + AgentExecutor integration     | Production-ready |
| LangGraph       | /langgraph              | StateGraph node + conditional edges              | Production-ready |
| CrewAI          | /crewai                 | Subclassed BaseTool + role-specific tools        | Production-ready |
| AutoGen         | /autogen                | register_function pattern                        | Production-ready |
| LlamaIndex      | /llamaindex             | FunctionTool (sync + async)                      | Production-ready |
| Haystack        | /haystack               | Custom @component gate                           | Production-ready |
| Semantic Kernel | /semantic-kernel        | .NET KernelFunction plugin (C#)                  | Production-ready |

More coming soon (AutoGPT, MetaGPT, DSPy, etc. — contributions welcome).

## Quick Start (any framework)

1. Install the PAS SDK  
   ```bash
   pip install singularitic...

   from singularitic import SingulariticClient
   pas = SingulariticClient(base_url="https://singularitic.com/api")
   pas.login("your-email@company.com", "your-password")  # or use api_key
