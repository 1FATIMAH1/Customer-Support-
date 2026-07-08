# Customer Support with Handoffs using LangGraph

An intelligent multi-agent customer support system built with **LangGraph**, **LangChain**, and **OpenAI**. The system automatically classifies customer requests, routes them to the appropriate support agent, retrieves relevant information using RAG, and escalates conversations to a human agent whenever required.

---

## Team Members

- Fatimah Alzeer

---

## Project Overview

This project implements the **Customer Support with Handoffs** architecture from the Building Agentic AI Systems capstone.

The assistant can:

- Classify customer requests.
- Route conversations to specialized support agents.
- Retrieve relevant knowledge from documents using RAG.
- Maintain conversation memory.
- Pause execution for human approval when escalation is required.
- Resume the workflow after human intervention.

---

## Features

- Multi-Agent Architecture
- Supervisor Agent
- Customer Support Agent
- Human Escalation (Handoff)
- Retrieval-Augmented Generation (RAG)
- Conversation Memory
- LangGraph Functional API
- LangSmith Tracing
- Error Handling
- Structured Outputs

---

## Tech Stack

- Python
- LangChain
- LangGraph
- OpenAI
- ChromaDB
- LangSmith

---


# Rubric Write-up

## 1. Agent Fundamentals

A working customer support agent was implemented using LangGraph. The agent makes real tool calls, generates structured outputs, and processes customer requests dynamically rather than relying on hardcoded responses.

---

## 2. Multi-Agent / Routing Architecture

The project follows the **Customer Support with Handoffs** pattern.

A supervisor agent determines whether a request can be answered automatically or should be escalated to a human support representative.

---

## 3. RAG Pipeline

The assistant uses a Retrieval-Augmented Generation (RAG) pipeline.

Documents are:

- Loaded
- Split into chunks
- Embedded
- Stored in a vector database
- Retrieved before generating responses

This project uses **2-Step RAG**, where retrieval occurs before response generation to improve answer accuracy while keeping the workflow simple and efficient.

---

## 4. Context & State Management

Conversation state is managed using LangGraph's checkpointer.

The system supports:

- Short-term memory for ongoing conversations.
- Persistent thread state across workflow execution.

---

## 5. Human-in-the-Loop

When the supervisor detects that a request requires manual review, the workflow pauses using `interrupt()` and waits for human approval before continuing.

This ensures that sensitive or complex customer issues receive human oversight.

---

## 6. LangGraph Functional API & Error Handling

The workflow is implemented using LangGraph's Functional API.

Implemented strategies include:

- User-fixable interrupt
- Transient retry

These improve workflow reliability and user experience.

---

## 7. Workflow Pattern

The project implements the **Routing** workflow pattern.

Incoming requests are classified and routed to the appropriate processing path based on their intent.

---

## 8. LangSmith Observability

LangSmith tracing is enabled to monitor workflow execution.

Tracing helped identify:

- Tool execution flow
- Agent routing decisions
- Response latency
- Potential workflow bottlenecks

