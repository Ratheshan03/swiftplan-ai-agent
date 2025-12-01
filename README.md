# ✈️ SwiftPlan: AI Travel Concierge
## Google x Kaggle AI Agents Intensive Capstone Project

**Track:** Concierge Agents
**Author:** Ratheshan Sathiyamoorthy
---

### 📖 Project Overview
SwiftPlan is a Multi-Agent System designed to eliminate the stress of travel planning. It automates the research and scheduling process, creating personalized, budget-conscious itineraries in seconds.

### 🏗️ Architecture & Key Concepts
This project demonstrates three key concepts from the course:

1.  **Multi-Agent System (Sequential):** * **Research Agent:** Uses Google Search (Grounding) to find real-time data on weather, attractions, and local culture.
    * **Planner Agent:** A reasoning engine that structures the raw data into a logical day-by-day plan.
    
2.  **Tools (Hybrid):** * **Google Search:** For external knowledge.
    * **Custom Python Tool (`currency_converter`):** A defined function that the agent actively calls to calculate budgets in local currency.

3.  **Observability & Memory:** * **Session Memory:** Maintains context across the research and planning phases.
    * **Logging:** Detailed console logs track the agent's thought process, tool usage, and execution status.

### Diagram

```mermaid
flowchart LR
    User([User]) --> SwiftPlan{{SwiftPlan App}}
    SwiftPlan -->|1. Task: Find activities & weather| ResearchAgent[Research Agent]
    ResearchAgent -->|Search Query| GoogleSearchTool[[Google Search Tool]]
    GoogleSearchTool -->|Search Results| ResearchAgent
    ResearchAgent -->|Research Data| SwiftPlan
    SwiftPlan -->|2. Task: Create itinerary + Data| PlannerAgent[Planner Agent]
    PlannerAgent -->|Convert Budget| CurrencyConverterTool[[Currency Converter Tool]]
    CurrencyConverterTool -->|Converted Amount| PlannerAgent
    PlannerAgent -->|Generated Itinerary| FinalItinerary[(Final Itinerary)]
    FinalItinerary -->|Output| User
```

### 🚀 How to Run
1.  Add your `GEMINI_API_KEY` in the **Add-ons -> Secrets** menu.
2.  Run all cells.
3.  Use the `run_swiftplan()` function at the bottom to test different destinations!
