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

## How to Read This Document
**Please read through whichever conceptual models interest you.**

This document presents n conceptual models. For example, they have names such as HASIO and OHAT — HASIO consists of Harness/Agent/Skill/Input Context/Output Contract, and OHAT consists of Orchestration/Harness/Agent/Tool. That is, after defining several conceptual units, it builds relationships among them.

The conceptual units themselves should be familiar to readers. For example, units like the following appear frequently:

- Harness
- Agent
- Skill

I think the strategy of Agentic Engineering can be said to be how to design the following two things:

- The meaning and responsibility of each conceptual unit
- The relationships between each conceptual unit

On that premise, this document names these two points "strategy" and presents n of them.

## Agentic Engineering Strategy v0.1

### HASIO
- Harness
    - Agent
        - Skill
            - Input Context
            - Output Contract

### HOAST
- Harness
    - Orchestration
        - Agent
            - Skill
                - Tool

### OHAST
- Orchestration
    - Harness
        - Agent
            - Skill
                - Tool

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
