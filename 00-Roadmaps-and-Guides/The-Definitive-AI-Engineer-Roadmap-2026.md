# 🧭 The Definitive AI Engineer Bookshelf & Reading Roadmap (2026 Edition)
### *A Practical Study & Implementation Companion for the 35+ Curated Books*

> **The Official Reading & Implementation Guide for this Bookshelf**  
> *Translating 35+ foundational to frontier books, research papers, and architecture manuscripts into hands-on milestones, production code, and technical interview mastery.*

---

## 📑 Table of Contents
1. [Executive Summary & The 2026 Mindset Shift](#1-executive-summary--the-2026-mindset-shift)
2. [The 3 Architectural Phases of This Bookshelf](#2-the-3-architectural-phases-of-this-bookshelf)
3. [The Complete 10-Stage Reading & Coding Roadmap](#3-the-complete-10-stage-reading--coding-roadmap)
   - [Stage 00: Foundations & Mental Model Transition](#stage-00-foundations--mental-model-transition)
   - [Stage 01: LLM Internals, Tokenization & Transformers](#stage-01-llm-internals-tokenization--transformers)
   - [Stage 02: Prompt Engineering & Output Guarantees (Layer 1)](#stage-02-prompt-engineering--output-guarantees-layer-1)
   - [Stage 03: Context Engineering & Advanced RAG (Layer 2)](#stage-03-context-engineering--advanced-rag-layer-2)
   - [Stage 04: Production Systems, FastAPI & LLMOps](#stage-04-production-systems-fastapi--llmops)
   - [Stage 05: Autonomous Agents & Cognitive Patterns](#stage-05-autonomous-agents--cognitive-patterns)
   - [Stage 06: Harness Engineering & Sandboxed Containment (Layer 3)](#stage-06-harness-engineering--sandboxed-containment-layer-3)
   - [Stage 07: Loop Engineering & Autonomous Feedback (Layer 4)](#stage-07-loop-engineering--autonomous-feedback-layer-4)
   - [Stage 08: Graph Engineering & Multi-Agent Topologies (Layer 5)](#stage-08-graph-engineering--multi-agent-topologies-layer-5)
   - [Stage 09: AI-Native Development & Vibe Coding](#stage-09-ai-native-development--vibe-coding)
   - [Stage 10: Reference Cheatsheets & Mathematical Index](#stage-10-reference-cheatsheets--mathematical-index)
4. [Master Technical Interview Preparation Guide](#4-master-technical-interview-preparation-guide)
5. [The 12-Week Bookshelf Reading & Production Timeline](#5-the-12-week-bookshelf-reading--production-timeline)

---

## 1. Executive Summary & The 2026 Mindset Shift

This roadmap serves as the **official reading companion and execution navigator** for the **AI Engineer Bookshelf**. It is structured to prevent "reading overload" by translating the 35+ volumes across directories `01` through `10` into a progressive, project-driven curriculum.

Between 2022 and 2026, software development underwent its greatest architectural transformation. Software engineering transitioned from **deterministic imperative programming** (where code explicitly dictates every execution step) to **probabilistic cognitive architecture** (where models reason over context and invoke sandboxed tools within strict graph boundaries):

```text
2022 - 2023 : Prompt Engineering   ──▶ Word & token phrasing
2023 - 2024 : Context Engineering  ──▶ Payload optimization & RAG
2024 - 2025 : Harness Engineering  ──▶ Sandboxed execution & tool containment
2025 - 2026 : Loop Engineering     ──▶ Autonomous generator-evaluator cycles
2026+       : Graph Engineering    ──▶ Multi-agent execution topologies & system intelligence
```

### The Coder-to-AI-Engineer Rule:
> **You do NOT need a PhD in Mathematics or deep expertise in training models from scratch.**  
> An AI Engineer treats the Foundation Model as a **probabilistic CPU** (reasoning engine). Your engineering leverage lives entirely in the **context pipelines, tool harnesses, evaluation loops, and multi-agent topologies** built around it.

---

## 2. The 3 Architectural Phases of AI Engineering

```text
┌────────────────────────────────────────────────────────────────────────┐
│ 📍 PHASE 1: GENERATIVE AI & FOUNDATION SYSTEMS (Stages 00 - 04)        │
│    Model is the computation center. Single-shot and stateless pipelines.│
│    [00 Roadmap] ──▶ [01 LLM Core] ──▶ [02 Prompt] ──▶ [03 RAG] ──▶ [04 LLMOps]
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │
                                   ▼
┌────────────────────────────────────────────────────────────────────────┐
│ 🤖 PHASE 2: AGENTIC AI & SYSTEM INTELLIGENCE (Stages 05 - 08)          │
│    Model is a component. Stateful runtime, tool calling, and graphs.   │
│    [05 Agents] ──▶ [06 Sandboxes] ──▶ [07 Evaluator Loop] ──▶ [08 Graphs]
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │
                                   ▼
┌────────────────────────────────────────────────────────────────────────┐
│ 🚀 PHASE 3: DEVELOPER WORKFLOW & CHEATSHEETS (Stages 09 - 10)          │
│    Engineering efficiency, intent programming, and mathematical index. │
│    [09 Vibe Coding / AI-Native Dev]  ──▶  [10 Stanford Cheatsheets]    │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 3. The Complete 10-Stage Learning Roadmap

---

### Stage 00: Foundations & Mental Model Transition
*Moving from Deterministic Backend Logic to Probabilistic Cognitive Architectures.*

- **Key Concepts**:
  - Deterministic software (f(x) → y) vs. Probabilistic completions (P(w_t | w_<t)).
  - The latency/cost/accuracy trade-off frontier.
  - Temperature, Top-P, and Top-K sampling mechanics.
  - "Evals > Vibes": Why qualitative eye-balling fails in production.
- **Production Tools**: Python 3.12+, Pydantic v2, Tiktoken, OpenAI / Anthropic APIs, Ollama.
- **Repository Literature**:
  - `00-Roadmaps-and-Guides/The-Definitive-AI-Engineer-Roadmap-2026.md` *(This Guide)*
- **Milestone Project**:
  - Build a CLI token counter and cost estimator for multi-provider API calls (OpenAI, Claude, DeepSeek) with dynamic streaming output.

---

### Stage 01: LLM Internals, Tokenization & Transformers
*Demystifying the black box: What happens between raw text and next-token prediction.*

- **Key Concepts**:
  - Byte-Pair Encoding (BPE), vocabulary dictionaries, and special tokens (`<|endoftext|>`).
  - Embedding projections: mapping discrete tokens into continuous vector spaces (R^d).
  - Scaled Dot-Product Attention:
    ```text
    Attention(Q, K, V) = softmax((Q * K^T) / sqrt(d_k)) * V
    ```
  - Multi-Head Attention, Causal Masking, LayerNorm (RMSNorm), and RoPE (Rotary Position Embeddings).
  - KV Caching: Why autoregressive generation consumes linear GPU VRAM per context token.
  - Model Quantization: FP16 vs. INT8 vs. INT4 (GGUF, AWQ, GPTQ).
- **Production Tools**: PyTorch, Hugging Face `transformers`, `tokenizers`, `accelerate`.
- **Repository Literature**:
  - `01-LLM-Foundations-and-Transformers/[Manning] Build a Large Language Model (From Scratch).pdf` *(Sebastian Raschka)*
  - `01-LLM-Foundations-and-Transformers/[O'Reilly] Natural Language Processing with Transformers.pdf` *(Hugging Face)*
- **Milestone Project**:
  - Implement a minimal GPT-2 decoder block from scratch in PyTorch, calculate causal cross-entropy loss, and generate tokens from a pre-trained checkpoint.

---

### Stage 02: Prompt Engineering & Output Guarantees (Layer 1)
*The linguistic steering layer: Forcing non-deterministic models into deterministic software interfaces.*

- **Key Concepts**:
  - In-Context Learning (ICL): Zero-shot, Few-shot prompting with balanced exemplars.
  - Reasoning scaffolds: Chain-of-Thought (CoT), Tree-of-Thought (ToT), Directional Stimulus.
  - Structured Output Enforcement: Constrained JSON schema generation, function calling conventions.
  - System Prompt Framing: Role definition, operational boundaries, fallback guardrails.
  - Anti-Jailbreaking & Defensive Prompting: Delimiter isolation, system instruction hierarchy.
- **Production Tools**: Instructor (Python), Pydantic, Outlines, LangChain Prompt Templates.
- **Repository Literature**:
  - `02-Prompt-Engineering/Prompt Engineering for Generative AI.pdf` *(O'Reilly, 843p)*
  - `02-Prompt-Engineering/Prompt Engineering Techniques.pdf` *(Practical LEGO Blocks)*
- **Milestone Project**:
  - Build a structured data extraction engine that parses messy multi-page invoices into validated, nested Pydantic models with automated schema retry on validation failure.

---

### Stage 03: Context Engineering & Advanced RAG (Layer 2)
*Information payload optimization: Grounding models with external truth and dynamic context.*

- **Key Concepts**:
  - The Context Window Budget: Prompt tokens, few-shot tokens, retrieved context, and completion buffer.
  - Semantic Chunking vs. Recursive Character Splitting (sliding windows, token overlap).
  - Dense vs. Sparse Hybrid Search (BM25 + Cosine Vector Similarity via Reciprocal Rank Fusion - RRF).
  - Cross-Encoder Reranking: Elevating top-k recall and mitigating "Lost-in-the-Middle" degradation.
  - Graph RAG: Transforming unstructured documents into typed entity-relation graphs for multi-hop reasoning.
  - Context Compression & Truncation: Summarization layers, selective KV cache re-use.
- **Production Tools**: Qdrant / Chroma / Pinecone, LlamaIndex, LangChain, Sentence-Transformers, Ragas.
- **Repository Literature**:
  - `03-Context-Engineering/Context Engineering for Large Language Models.pdf` *(Lingrui Mei et al. 166p Survey)*
  - `03-Context-Engineering/Graph Retrieval-Augmented Generation (Graph RAG) - A Survey.pdf`
  - `03-Context-Engineering/Generative AI with LangChain (Dr. Priyanka Singh Hariom Singh).pdf`
- **Milestone Project**:
  - Build a Production Hybrid RAG system over technical documentation: PDF parsing, semantic chunking, Qdrant hybrid search (dense + BM25), BGE-Reranker, and Ragas automated evaluation for Context Precision and Faithfulness.

---

### Stage 04: Production Systems, FastAPI & LLMOps
*Packaging models into high-concurrency, low-latency, observable enterprise microservices.*

- **Key Concepts**:
  - Server-Sent Events (SSE) & WebSocket streaming architectures.
  - Asynchronous concurrency with Python `asyncio` and non-blocking I/O.
  - Prompt Caching: Reusing KV cache prefixes across API requests to reduce latency by 80% and cost by 50%.
  - Guardrails & Safety: Input content moderation, output PII masking, OWASP Top 10 for LLMs.
  - Observability & Tracing: Spans, token usage tracking, latency breakdown (TTFT - Time to First Token).
  - CI/CD Test Gates: Running continuous LLM evaluations against golden datasets before deployment.
- **Production Tools**: FastAPI, Redis, Docker, Langfuse, LangSmith, Arize Phoenix, LiteLLM.
- **Repository Literature**:
  - `04-AI-Engineering-and-System-Design/Building Generative AI Services with FastAPI A Practical Approach to Developing Context-Rich Generative AI Applications (Alireza Parandeh).pdf`
  - `04-AI-Engineering-and-System-Design/AI Engineering Building Applications with Foundation Models (Chip Huyen).pdf`
  - `04-AI-Engineering-and-System-Design/[O'Reilly] Designing Machine Learning Systems.pdf` *(Chip Huyen)*
  - `04-AI-Engineering-and-System-Design/[O'Reilly] What is LLMOps_Large Language Models in Production.pdf`
- **Milestone Project**:
  - Deploy a containerized FastAPI service with token streaming (SSE), Redis semantic response cache, LiteLLM unified routing, and Langfuse tracing.

---

### Stage 05: Autonomous Agents & Cognitive Patterns
*Designing agents that perceive, plan, remember, and call tools toward high-level goals.*

- **Key Concepts**:
  - Cognitive Core: Perception → Memory → Planning → Action.
  - Reasoning Patterns: ReAct (Reason + Act), Plan-and-Solve, Reflexion (Self-Reflection).
  - Tool Calling Conventions: Model Context Protocol (MCP) by Anthropic, OpenAI Tool Calling schema.
  - Memory Systems:
    - Working Memory: In-context dynamic window.
    - Episodic Memory: Vector-embedded conversation logs.
    - Semantic Memory: Entity knowledge graphs.
  - Multi-Agent Collaboration: Supervisor pattern, hierarchical delegation, peer-to-peer swarms.
- **Production Tools**: LangGraph, AutoGen, CrewAI, Model Context Protocol (MCP) SDK, Google ADK.
- **Repository Literature**:
  - `05-AI-Agents-and-Autonomous-Systems/AI Agents The Definitive Guide` *(Nicole Koenigstein)*
  - `05-AI-Agents-and-Autonomous-Systems/Agentic_Design_Patterns.pdf` *(EECS UC Berkeley - 21 Patterns)*
  - `05-AI-Agents-and-Autonomous-Systems/[O'Reilly] Generative AI Design Patterns.pdf`
  - `05-AI-Agents-and-Autonomous-Systems/Building Applications with AI Agents (Fifth Early Release) (Michael Albada).pdf`
- **Milestone Project**:
  - Build an autonomous GitHub Research Agent using MCP: connects to GitHub API, inspects open issues, searches repository files, clones repo, and writes a diagnostic summary report.

---

### Stage 06: Harness Engineering & Sandboxed Containment (Layer 3)
*Building the containment runtime: Tool isolation, permission models, and session persistence.*

- **Key Concepts**:
  - The Harness Definition: The infrastructure that surrounds the LLM to control what it can touch.
  - Security containment: Ephemeral Docker containers, E2B microVM sandboxes, gVisor isolation.
  - OS Bash Firewalls: Command whitelisting, preventing destructive operations (`rm -rf /`, credential exfiltration).
  - Session Persistence: Managing subagent states, compaction of long tool outputs, token budget ceilings.
  - Claude Code & Codex architectural teardowns: How frontier coding agents manage tool loops safely.
- **Production Tools**: Docker, E2B Sandboxes, gVisor, Subprocess controllers, Pydantic guardrails.
- **Repository Literature**:
  - `06-Harness-Engineering/Harness-Engineering-The-Complete-Guide.pdf` *(HuaShu)*
  - `06-Harness-Engineering/The Harness Design Philosophies of Claude Code and Codex.pdf`
  - `06-Harness-Engineering/Claude Code The Definitive Guide to Agentic Development.pdf`
- **Milestone Project**:
  - Create a sandboxed Python code execution harness using E2B or Docker: agent submits Python code, executes in an isolated environment with strict 5-second timeouts, captures stdout/stderr, and returns clean structured telemetry to the planner.

---

### Stage 07: Loop Engineering & Autonomous Feedback (Layer 4)
*Generator vs. Evaluator separation: Self-healing runtimes with explicit stopping conditions.*

- **Key Concepts**:
  - The Generator-Evaluator Dichotomy: **An AI cannot objectively grade its own code**.
  - Dual-Context Architecture: Generator has full write context; Evaluator operates in a fresh, clean, read-only verification context.
  - Stopping Conditions: Maximum iteration ceilings, delta-improvement thresholds, regression detection.
  - Self-Healing Test Gates:
    1. Generator writes code diff.
    2. Test Gate executes Pytest / linter.
    3. Failure stack traces parsed and formatted into minimal error payloads.
    4. Feedback fed into generator until tests pass or budget exhausted.
- **Production Tools**: Pytest, Ruff, LLM-as-a-Judge frameworks, MT-Bench evaluation harnesses.
- **Repository Literature**:
  - `07-Loop-Engineering/Loop-Engineering-The-Complete-Guide.pdf` *(AI Systems Research)*
  - `07-Loop-Engineering/Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena.pdf` *(LMSYS)*
  - `07-Loop-Engineering/Practices for Governing Agentic AI Systems.pdf` *(Yonadav Shavit et al. - OpenAI)*
  - `07-Loop-Engineering/Constitutional AI - Harmlessness from AI Feedback.pdf` *(Yuntao Bai et al. - Anthropic)*
  - `07-Loop-Engineering/Self-Refine - Iterative Refinement with Self-Feedback.pdf` *(Aman Madaan et al. - CMU / NeurIPS)*
  - `[The Shift from Models to Compound AI Systems](https://bair.berkeley.edu/blog/2024/02/18/compound-ai-systems/)` *(Matei Zaharia et al. - UC Berkeley BAIR)*
- **Milestone Project**:
  - Build an Autonomous Bug-Fixing Loop: given a failing unit test, the agent reads the test file, edits production code, runs pytest inside a sandbox, inspects errors, and iterates until the test suite passes 100% green without human intervention.

---

### Stage 08: Graph Engineering & Multi-Agent Topologies (Layer 5)
*Stateful execution graphs (G_A) and knowledge memory graphs (G_K): The 2026 frontier.*

- **Key Concepts**:
  - Execution Graphs (G_A): Modeling multi-agent workflows as Directed Acyclic Graphs (DAGs) or Cyclic StateGraphs.
  - The Diamond Task Pattern:
    ```text
    Planner → Parallel Workers {W1, W2, ... Wn} → Isolated Verifiers {V1, V2, ... Vn} → Single Barrier Join
    ```
  - Dynamic Fan-Out / Fan-In: Splitting large documents into parallel worker nodes and reducing to a unified state.
  - Human-in-the-Loop Checkpointing: Pausing execution graph at high-risk nodes (deployments, financial transactions) and resuming via serialized state.
  - GraphRAG (G_K): Integrating structured Neo4j / NetworkX knowledge graphs with agent memory.
- **Production Tools**: LangGraph, Neo4j, NetworkX, Postgres Checkpointer.
- **Repository Literature**:
  - `08-Graph-Engineering-and-System-Intelligence/Engineering Agent Graphs - Architecture, Topologies, and Production Governance.pdf`
  - `08-Graph-Engineering-and-System-Intelligence/Graph Engineering in the Era of LLM Agents.pdf`
  - `08-Graph-Engineering-and-System-Intelligence/Graph Engineering - The Definitive Guide to Knowledge Graphs and Agent Task Graphs.pdf`
- **Milestone Project**:
  - Implement a Multi-Agent Software Review System with LangGraph: Planner decomposes PR diff → Security Agent, Performance Agent, and Style Agent analyze in parallel → Isolated Verifier nodes validate findings → Single Barrier Join produces unified GitHub review comments.

---

### Stage 09: AI-Native Development & Vibe Coding
*The practitioner's workflow: How high-leverage software engineers code in the AI era.*

- **Key Concepts**:
  - Intent Programming: Writing specifications, architectural constraints, and test suites while delegating implementation to agent loops.
  - AI Pair Programming Mastery: Claude Code, Cursor, Antigravity, GitHub Copilot.
  - Context Curation: Feeding agents minimal high-signal context (interfaces, types, docs) rather than entire codebases.
  - Avoiding AI Slop: Guarding code quality, architecture integrity, and performance against generic LLM boilerplate.
- **Production Tools**: Claude Code, Cursor, Codex, Ripgrep, Ast-Grep.
- **Repository Literature**:
  - `09-Vibe-Coding-and-AI-Assisted-Dev/Vibe Coding The Future of Programming (First Early Release).pdf` *(Gene Kim & Steve Yegge)*
  - `09-Vibe-Coding-and-AI-Assisted-Dev/[O'Reilly] Beyond Vibe Coding From Coder to AI-Era Developer.pdf`
  - `09-Vibe-Coding-and-AI-Assisted-Dev/Agentic Coding for beginners (Wasi).pdf`
- **Milestone Project**:
  - Scaffold a full-stack CRUD application in under 2 hours using purely AI-assisted intent workflows: write `SPEC.md`, generate tests first, and direct an agent to implement all backend routes and frontend components.

---

### Stage 10: Reference Cheatsheets & Mathematical Index
*Quick-reference cards, mathematical formulas, and system design cheats.*

- **Key Concepts**:
  - Transformer attention equations and dimension matching (`d_model, d_k, d_v, h`).
  - KV Cache VRAM calculation formula:
    ```text
    VRAM_KVCache = 2 * n_layers * n_heads * d_head * seq_len * batch_size * precision_bytes
    ```
  - Token-to-word heuristics: 1 token ≈ 0.75 English words (1,000 tokens ≈ 750 words).
- **Repository Literature**:
  - `10-Reference-and-Cheatsheets/Stanford Cheatsheet - Transformers and Large Language Models.pdf` *(Afshine & Shervine Amidi, Stanford)*
  - `10-Reference-and-Cheatsheets/Agentic-Design-Architecture-A-Reskilling-Curriculum-for-the-AI-Native-Enterprise.pdf`
  - `10-Reference-and-Cheatsheets/ai-agents-cheat-sheet.pdf`

---

## 4. Master Technical Interview Preparation Guide
*(Synthesized from Production AI Engineering Interview Loops)*

### Domain 1: LLM Architecture & Systems Design
1. **Question**: *What is KV Caching, why is it necessary, and how does it affect GPU VRAM during serving?*
   - **Answer**: In autoregressive LLMs, generating each new token requires attending to all previous tokens. Without KV caching, the Key and Value matrices for all preceding tokens would need to be recomputed at every forward pass (O(N²) compute). KV caching stores past K and V vectors in GPU memory, making token generation O(1) compute per step at the cost of linear VRAM growth (O(N) memory per active sequence).

2. **Question**: *Explain the difference between Bi-Encoder and Cross-Encoder architectures in RAG.*
   - **Answer**: A **Bi-Encoder** (like standard embedding models) encodes queries and documents independently into fixed-size dense vectors. Similarity is computed via fast vector dot-product/cosine similarity (O(1) lookup via ANN indexes), making it fast for searching millions of docs. A **Cross-Encoder** feeds both query and document simultaneously into the transformer with full cross-attention across all tokens. It is significantly more accurate at semantic scoring but orders of magnitude slower, which is why it is used as a **2nd-stage Reranker** on only the top 20–50 candidates.

3. **Question**: *How do you mitigate the "Lost-in-the-Middle" phenomenon in long context windows?*
   - **Answer**: LLMs recall information placed at the extreme beginning and end of long contexts with much higher fidelity than tokens in the middle. Mitigation strategies: (1) Reranking documents so the most relevant chunk is placed either at the very top or directly before the generation prompt; (2) Semantic chunk deduplication and compression to minimize total payload size; (3) Multi-hop Map-Reduce summarization; (4) Using models fine-tuned with RoPE scaling and attention masking optimizations.

### Domain 2: Agent Systems & Execution Governance
4. **Question**: *What is the Model Context Protocol (MCP) and what problem does it solve?*
   - **Answer**: Before MCP, every AI developer wrote proprietary, ad-hoc wrapper code to connect LLMs to databases, APIs, and file systems. **Model Context Protocol (MCP)** standardizes how an agent discovers available tools, reads external resources, and executes operations through a uniform, client-server protocol over stdio or SSE. It enables plug-and-play interoperability across any LLM platform.

5. **Question**: *Why must the Evaluator and Generator have separate contexts in an autonomous loop?*
   - **Answer**: If the Generator agent evaluates its own output, it suffers from self-justifying confirmation bias—it re-reads its own flawed assumptions in its context history and rationalizes errors. Separating them into a **Generator Node** (write access) and an **Evaluator Node** (clean, read-only context containing only objective criteria, test assertions, and lint results) enforces rigorous quality gates.

6. **Question**: *What is the Diamond Topology in multi-agent graph engineering?*
   - **Answer**: The Diamond Pattern decomposes a complex task into: (1) **Planner Node** generates subtasks → (2) **Dynamic Fan-Out** dispatches subtasks to parallel worker agents → (3) **Isolated Verifiers** inspect each worker's output in clean contexts → (4) **Barrier Join** synchronizes and merges verified states into a single unified output state. This prevents race conditions and state corruption.

---

## 5. The 12-Week Production Mastery Timeline

| Week | Phase | Focus & Milestones | Primary Literature |
| :---: | :---: | :--- | :--- |
| **W1&ndash;W2** | **Phase 1** | Python async, PyTorch attention mechanics, BPE tokenization, building GPT-2 block from scratch. | *Sebastian Raschka (01)* & *Stanford Cheatsheet (10)* |
| **W3&ndash;W4** | **Phase 1** | Prompt Engineering, few-shot reasoning, Pydantic structured output, schema extraction. | *O'Reilly Prompt Eng (02)* |
| **W5&ndash;W6** | **Phase 1** | Advanced RAG: Hybrid search (BM25 + Dense), Cross-Encoder reranking, Qdrant, Ragas evals. | *Lingrui Mei Survey (03)* & *LangChain (03)* |
| **W7&ndash;W8** | **Phase 1** | Production FastAPI: Streaming SSE, prompt caching, token cost tracking, Langfuse tracing. | *Alireza Parandeh (04)* & *Chip Huyen (04)* |
| **W9&ndash;W10** | **Phase 2** | Autonomous Agents: ReAct, tool calling, MCP servers, Docker/E2B sandbox containment. | *Nicole Koenigstein (05)* & *Harness Guide (06)* |
| **W11** | **Phase 2** | Loop Engineering: Generator-evaluator separation, self-healing Pytest loops, MT-Bench. | *Loop Engineering (07)* |
| **W12** | **Phase 2** | Graph Engineering: LangGraph stategraphs, Diamond pattern, human checkpointing, deployment. | *Engineering Agent Graphs (08)* |

---

*This document is the official Roadmap of the 2026 AI Engineer Bookshelf. Maintained with pride for the global AI Engineering community.*
