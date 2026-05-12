# Two‑Tier Cognition Framework (TTCF)

### A cognitive architecture for LLM agents based on a strict separation between high‑level reasoning and deterministic domain tools.

**Author:** Arkadiusz Sieracki  
**Version:** v0.1  
**Status:** Draft Specification

---

# 1. Overview

The **Two‑Tier Cognition Framework (TTCF)** is a cognitive architecture for building predictable, controllable and scalable LLM‑based agents.  
It introduces a strict separation between:

- **Tier 1 — High‑Level Cognition**  
  LLM performs planning, intent interpretation and tool selection.

- **Tier 2 — Deterministic Domain Tools**  
  Execution is delegated to small, atomic, non‑interpretable, deterministic modules.

This separation mirrors how human cognition works:  
**the mind plans, the body executes**.

TTCF provides a foundation for agent systems that avoid hallucinations, drift and over‑interpretation by removing low‑level reasoning from the LLM entirely.

---

# 2. Motivation

Current agent architectures fail for three reasons:

1. **LLMs mix high‑level and low‑level reasoning**  
   They try to plan _and_ execute, which leads to drift, inconsistency and hallucinations.

2. **LLMs are not deterministic at low‑level tasks**  
   They cannot reliably perform precise operations, transformations or domain‑specific logic.

3. **Tools are too generic**  
   Agents rely on broad, ambiguous tools that still require interpretation.

TTCF solves these issues by enforcing a **hard cognitive boundary**.

---

# 3. The Two Tiers

## Tier 1 — High‑Level Cognition (LLM)

The LLM is responsible for:

- interpreting user intent
- decomposing tasks
- selecting tools
- generating parameters
- orchestrating execution
- validating outcomes

It **does not** perform domain logic.

### Responsibilities

Intent → Plan → Select Tool → Provide Arguments → Evaluate Result

Kod

### Properties

- probabilistic
- contextual
- flexible
- creative
- non‑deterministic

This is where LLMs shine.

---

## Tier 2 — Deterministic Domain Tools

Tools are:

- small
- atomic
- domain‑specific
- deterministic
- non‑interpretable
- context‑free

They perform **one** operation and always produce the same output for the same input.

### Responsibilities

Execute → Return Result → No Interpretation

Kod

### Properties

- predictable
- testable
- safe
- reproducible
- fully controlled

This is where software shines.

---

# 4. Architecture Diagram

## High‑Level View

┌──────────────────────────────┐
│ Tier 1 — LLM │
│ High‑Level Cognition │
│ • Intent interpretation │
│ • Planning │
│ • Tool selection │
│ • Parameter generation │
└───────────────┬──────────────┘
│
▼
┌──────────────────────────────┐
│ Tier 2 — Domain Tools │
│ Deterministic Execution │
│ • Atomic operations │
│ • No interpretation │
│ • Predictable outputs │
└──────────────────────────────┘

Kod

---

## Cognitive Flow

User Intent
│
▼
[ Tier 1: LLM ]
"To achieve X, call tool Y with parameters Z."
│
▼
[ Tier 2: Tool ]
Executes deterministically
│
▼
Result returned to LLM
│
▼
LLM evaluates → continues or stops

Kod

---

# 5. Example

### User request:

> "Generate a dependency graph for this Python project."

### Tier 1 (LLM):

- Understands intent
- Chooses tool: `analyze_dependencies`
- Generates parameters: path, depth, format
- Calls tool

### Tier 2 (Tool):

- Parses project
- Builds graph deterministically
- Returns JSON

### Tier 1 (LLM):

- Converts JSON to Mermaid
- Returns final answer

---

# 6. Why TTCF Works

### 1. **Predictability**

LLM never performs low‑level logic → no hallucinations in execution.

### 2. **Determinism**

Tools are testable and reproducible.

### 3. **Scalability**

New tools = new capabilities without retraining.

### 4. **Safety**

LLM cannot improvise execution logic.

### 5. **Modularity**

Each tool is a small, isolated domain module.

### 6. **Human‑like cognition**

Planning and execution are separated — just like in biological intelligence.

---

# 7. Design Principles

- **LLM plans, tools execute**
- **Tools must be atomic**
- **Tools must be deterministic**
- **LLM must never interpret tool outputs incorrectly**
- **LLM must never perform domain logic**
- **All domain logic must live in Tier 2**
- **Tier 1 must be stateless and context‑driven**
- **Tier 2 must be testable and isolated**

---

# 8. Roadmap

### v0.2

- Formal TTCF specification
- Expanded diagrams
- Reference implementation

### v0.3

- Example agent built on TTCF
- Domain tool library

### v1.0

- Full standard
- Validation suite
- Community contributions

---

# 9. License

Apache 2.0

---

# 10. Citation

If you use TTCF in research or production, please cite:

**Sieracki, Arkadiusz. "Two‑Tier Cognition Framework (TTCF): A Cognitive Architecture for LLM Agents." 2026.**
