# 🧞 The Day Trip Genie

An AI-powered day trip planner built with **Google's Agent Development Kit (ADK)** and **Gemini**. Given a user's preferences (budget, vibe, location), the agent reasons through options and generates a structured, markdown-formatted day itinerary — complete with budget-aware recommendations.

This project was built as part of the [Google ADK Crash Course Codelab](https://codelabs.developers.google.com/onramp/instructions#0) — *From Beginner to Expert*.

---

## 📁 Repository Structure

```
The-Day-Trip-Genie/
├── The_Day_Trip_Genie.ipynb              # Single-agent implementation
├── The_Day_Trip_Genie(MultiAgents).ipynb # Multi-agent implementation
└── README.md
```

---

## 🧠 What It Does

The Day Trip Genie is an AI agent that:

- Accepts user preferences like budget, mood, and location context
- Uses **Google Search** as a built-in tool to find real, up-to-date trip options
- Generates a full-day itinerary in a clean markdown format
- Handles multi-turn conversations using **Session memory**
- Delegates tasks to sub-agents in the multi-agent version

---

## 📓 Notebooks

### `The_Day_Trip_Genie.ipynb` — Single Agent

Introduces the three core components of any ADK agent interaction:

| Component | Role |
|-----------|------|
| **Agent** | The brain — defined by instructions, model (Gemini), and tools |
| **Session** | The memory — stores conversation history for multi-turn dialogue |
| **Runner** | The engine — processes user queries and drives execution |

The agent uses a custom `run_day_trip_genie()` function to simulate a user asking for an "affordable" and "relaxing" day trip. It leverages Google Search to ground its recommendations in real results.

Also demonstrates **custom tool creation** from Python functions — the ADK auto-parses docstrings to understand tool capabilities, parameters, and return values.

### `The_Day_Trip_Genie(MultiAgents).ipynb` — Multi-Agent System

Extends the single-agent design into a coordinated multi-agent pipeline using ADK's workflow agents:

| Agent Type | Purpose |
|------------|---------|
| `SequentialAgent` | Runs sub-agents one after another in order |
| `ParallelAgent` | Runs multiple sub-agents simultaneously |
| `LoopAgent` | Iteratively refines output until a condition is met |
| Agent-as-a-Tool | One agent delegates a task to another agent as a callable tool |

---

## 🛠️ Tech Stack

- **Language:** Python
- **Framework:** [Google Agent Development Kit (ADK)](https://google.github.io/adk-docs/)
- **Model:** Gemini (via Google AI)
- **Tools:** Google Search (built-in ADK tool)
- **Environment:** Google Colab (no local setup required)

---

## 🚀 Getting Started

### Prerequisites

- A Google account (for Colab)
- A **Gemini API key** from [Google AI Studio](https://aistudio.google.com/)

### Run in Google Colab

1. Open either notebook directly in GitHub and click **"Open in Colab"**, or upload it manually at [colab.research.google.com](https://colab.research.google.com).
2. Set your Gemini API key when prompted (or store it as a Colab secret).
3. Run all cells in order.

---

## 💡 Key Concepts Learned

- How to define an ADK `Agent` with a system instruction, model, and tools
- How `Session` and `Runner` work together to power multi-turn conversations
- How to write Python functions as **custom ADK tools** using docstrings
- How to compose agents using `SequentialAgent`, `ParallelAgent`, and `LoopAgent`
- The **Agent-as-a-Tool** pattern for hierarchical agent delegation

---

## 📚 Reference

- [Google ADK Documentation](https://google.github.io/adk-docs/)
- [ADK Crash Course Codelab](https://codelabs.developers.google.com/onramp/instructions#0)
- [Google AI Studio (API Keys)](https://aistudio.google.com/)
