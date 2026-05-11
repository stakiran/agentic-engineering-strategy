# Agentic Engineering Strategy
[日本語](index.md) | [English](index_EN.md) | [GitHub](https://github.com/stakiran/agentic-engineering-strategy)

## Introduction

### What is Agentic Engineering?
A concept proposed by Andrej Karpathy — who advocated Vibe Coding in 2025 — as the 2026 version of how things should be.

- <https://x.com/karpathy/status/2019137879310836075>

Humans hardly write code directly. Instead, they delegate it to AI, and the human's main job becomes orchestrating AI — particularly groups of agents — and supervising their behavior. This activity also has depth, and seems to leave room for reproducibility.

The name of this "likely-to-come trend" is undecided, but Karpathy posted that he likes "Agentic Engineering." He also wrote nuances such as spending 99% of one's time on orchestration and supervision, and that engineering involves craft, theory, and (specialized expertise to be acquired).

In this document, let us define it as follows:

Agentic Engineering is **the trend in which humans write no code at all, or hardly any, and instead delegate the work to AI agents.**

As the name suggests, Agentic Engineering has two characteristics:

- As the word "agent" indicates, generative AI is captured and delegated to as a unit called an "agent"
- As the word "engineering" indicates, enough knowledge is in place — or coming into place — to organize this as an engineering discipline

A manager does not move their own hands; they skillfully manage their subordinates, who are complex humans. Likewise, in Agentic Engineering, we ourselves must become managers and skillfully manage our subordinates — the AI agents. And this activity has reached a level where it can be, or nearly can be, systematized.

A familiar example would be Prompt Engineering. There are many textbooks and papers on this topic. Agentic Engineering will likely follow suit, but as of 2026-05-10 it is still unorganized.

### What is Agentic Engineering Strategy?
Let us get to the main topic.

Agentic Engineering Strategy refers to **proposed architectures for AI agents** that realize Agentic Engineering. It does not have the concreteness or effectiveness to be called a pattern; at the level of conceptual models, it presents proposals such as "if you place these concepts and relationships like this, things might go well." In other words, it is a strategy. Or you may call it an approach.

The purpose of Agentic Engineering Strategy is to give reference and inspiration to fellow practitioners who aspire to this activity.

## The Intent of This Document and How to Read It

### Please read through whichever conceptual models interest you!
This document presents n conceptual models.

For example, they have names such as HASIO and OHAT — HASIO consists of Harness/Agent/Skill/Input Context/Output Contract, and OHAT consists of Orchestration/Harness/Agent/Tool. That is, after defining several conceptual units, it builds relationships among them.

At this point, we cannot say which model is right or wrong. Rather, it is a matter of decision-making.

**What kind of conceptual model should you, your team, or your product build? And why build it that way?**

I believe what is most important is to hold onto this question and keep walking forward. This document should serve as a good hint.

### Why Conceptual Models?
The conceptual units themselves should be familiar to readers. For example, units like the following appear frequently:

- Harness
- Agent
- Skill

On a personal note, I am working on something even more ambitious than Agentic Engineering. I have named it FASD (Fully Autonomous Software Development), and in the spirit of 12 Factor Agents, I have also organized [12 Factor FASD (Fully Autonomous Software Development)](https://stakiran.github.io/12-factor-fasd/). In other words, including Agentic Engineering, I am in a position not only of practice but also of research.

I have gradually come to feel that **architecture is also important in Agentic Engineering**. The reason is that simply using agents in a sloppy way cannot ensure quality, nor can we fulfill our accountability for measuring and explaining what is and is not possible. Despite this, at present, each engineer either entrusts things to their own intuition, multiplies their moves the way business does, or spends their days trying out and catching up on open-source agent/harness frameworks.

Perhaps we must not run away. Just as a capable manager builds systems based on their convictions, we Agentic Engineers must do the same. The word "architecture" should be useful here. Saying "build an architecture" gets the message across easily. So then, what is architecture in Agentic Engineering?

I thought what is needed first is **"clarity" and "an entry point."** So I decided to simply think about conceptual units and their relationships. I call this a conceptual model, and this document is a catalog of conceptual models.

By the way, as for the conceptual units, I have brought in ones that are already well known. However, since they are polysemous, I will firmly define their meanings within each model.

## Agentic Engineering Strategy v0.1

### Terminology
- Governance: controlling settings that apply to "every LLM call," such as overall control via the harness file, switching the model in use, and monitoring context consumption
- Governance Parameters: settings and instructions related to governance
- Local Context: context that is valid within one's own scope. It may also be passed down to subordinates
- Global Context: of the contexts that **can be referenced** from every LLM call, the portion excluding governance

### HOAST
- Harness
    - Orchestration
        - Agent
            - Skill
                - Tool

Conceptual units:

- Harness: bears the **governance** of orchestration and agents
- Orchestration: handles how multiple agents are coordinated. Contains **local context**
- Agent: performs some job using multiple skills. Contains **local context**
- Skill: processing packaged in a reusable form
- Tool: handles part of a skill's processing. Deterministic. Closed within the skill

Relationships:

- 1 Harness has n Orchestrations
- 1 Orchestration has n Agents
- 1 Agent references n Skills
- 1 Skill has n Tools

Notes:

- AST is the golden pattern
    - An agent is a clean, well-bounded unit that contains non-deterministic prompt-driven processing
    - A skill is what is carved out as a reusable component, like a function or module
    - A tool is a **deterministic** program or external call that does not rely on non-determinism
        - For stability of results and performance, parts that can be implemented deterministically should be implemented that way
        - Note that tools are not given reusability; they may be hard-coded into their owning skill. Even when you want to reuse one, duplicate it instead. This means tools are not regarded as architecture. There are two reasons: 1) we want to focus on Agentic Engineering; 2) tools can be created by the AI on a per-skill basis as needed
- Orchestration does not carry governance, so engineers can focus on the logic of orchestration
- On the other hand, since governance is controlled by the topmost harness, governance parameters must be propagated down to the agents

By way of analogy: the harness is like the organization, the orchestration is like a supervisor, and the agent is like a worker. Both the orchestration and the agent are employees, and cannot defy the organization's principles.

### OHAST
- Orchestration
    - Harness
        - Agent
            - Skill
                - Tool

Conceptual units:

- Orchestration: handles how multiple harnesses are coordinated
- Harness: wraps agents and bears overall control, including performance (capability, cost, quality)
- Agent: performs some job using multiple skills. Contains prompts and context
- Skill: processing packaged in a reusable form. Contains prompts
- Tool: handles part of a skill's processing. Deterministic. Closed within the skill

Relationships:

- 1 Orchestration has n Harnesses
- 1 Harness has 1 Agent
- 1 Agent references n Skills
- 1 Skill has n Tools

Notes:

- AST is the golden pattern
    - (omitted)
- Unlike HOAST, the harness wraps the agent
    - Therefore governance parameters are held on a per-agent basis
    - However, orchestration is not wrapped in a harness

Agents have higher autonomy than in HOAST. For example, they can burst processing on their own judgment, putting pressure on cost or the context window. However, since orchestration exists, supervision is still possible.

The concern is **runaway orchestration**. Because it is not wrapped in a harness, it tends to become an unrestrained zone or a vulnerability. For that reason, orchestration itself should not perform processing and should delegate as much as possible to the agents. Still, as the supervisor of agents, it should bear at least minimum control. How to strike this balance in implementation is the hard part.

### OHAT
- Orchestration
    - Harness
        - Agent
            - Tool

### HASK
- Harness
    - Agent
        - Skill
        - Knowledge

### RHAS
- Remuda
    - Harness
        - Agent
            - Skill

### HASIO
- Harness
    - Agent
        - Skill
            - Input Context
            - Output Contract
