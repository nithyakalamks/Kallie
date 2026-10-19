Kallie — AI Delivery Call Assistant

Making delivery coordination invisible with AI voice agents.

Kallie is an AI-powered voice assistant that handles delivery calls on behalf of customers, so they don’t have to interrupt meetings, work, or personal time to answer repetitive delivery questions.

🚧 Status: MVP in progress | Initial voice agent prototype built using xAI Voice Agents.

⸻

🎯 The Problem

How might we help customers receive their deliveries at their doorstep without having to interrupt their day to answer delivery calls and repeat instructions?

Customers frequently receive delivery calls to:

* Confirm their availability to receive a package.
* Clarify their address, landmarks, floor, or entrance.
* Communicate building access and delivery instructions.
* Coordinate alternative delivery times when unavailable.

These interruptions create friction for customers and delays for delivery agents.

💡 The Solution

Kallie acts as a customer’s AI delivery assistant.

Instead of answering every delivery call, customers can provide their delivery preferences and instructions to Kallie. The voice agent communicates relevant information to delivery agents, handles routine questions, and records the outcome.

Example Interaction

Delivery agent: I’m at your location, but I can’t find your building entrance.

Kallie: The entrance is beside the pharmacy. The building is called Greenwood Apartments.

Delivery agent: Which floor should I go to?

Kallie: The apartment is on the third floor. Please ring the doorbell when you arrive.

Illustrative conversation. Actual behaviour depends on the information available to the agent.

⸻

🧠 AI Product Challenges

Kallie explores the challenges involved in building a reliable AI voice agent beyond simply making it speak.

1. Context Management

* Retrieve relevant customer delivery instructions.
* Maintain context throughout a conversation.
* Handle follow-up questions without repeatedly asking for the same information.
* Distinguish between known information and missing information.

2. Accuracy and Hallucination Prevention

* Provide only information supported by customer instructions or verified context.
* Never invent addresses, landmarks, access codes, or delivery preferences.
* Ask for clarification when information is missing or ambiguous.

3. Conversation and Exception Handling

* Handle unexpected questions and changes in delivery plans.
* Recognise when a request cannot be resolved autonomously.
* Escalate unresolved situations rather than making assumptions.

4. Evaluation and Reliability

Evaluate the agent using defined test scenarios and measurable outcomes.

Metric	What it measures
Task completion rate	Whether the agent achieves the intended outcome
Instruction accuracy	Whether customer instructions are communicated correctly
Unsupported-claim rate	How often the agent states information without evidence
Fallback rate	How often the agent needs clarification or human intervention
Response latency	How quickly the agent responds during a call

These are proposed evaluation metrics; production performance has not yet been established.

⸻

🏗️ Proposed Architecture

Customer Delivery Preferences
            |
            v
Customer Context / Instructions
            |
            v
      AI Voice Agent
         (xAI)
            |
            v
  Delivery Conversation
            |
            v
  Outcome & Exception Logging
            |
            v
    Workflow Automation
          (n8n)
            |
            v
    Customer / Call Records
      (Google Sheets)

Note: This represents the proposed architecture, not a claim that every component is currently integrated.

Technology Stack

Component	Technology	Status
Voice AI	xAI Voice Agents	Initial prototype built
Workflow automation	n8n	Planned
Call outcome storage	Google Sheets	Planned
Telephony	Twilio	Planned
Evaluation	Scenario-based testing and defined metrics	To be implemented

⸻

🧪 MVP Scope

In Scope

* Simulate delivery confirmation conversations.
* Clarify address and delivery instructions.
* Handle basic availability and rescheduling scenarios.
* Maintain relevant conversation context.
* Define guardrails for missing information and unexpected requests.
* Design an evaluation framework for agent reliability.

Out of Scope for the Initial MVP

* Fully autonomous handling of every real delivery call.
* Integration with multiple delivery platforms.
* Guaranteed delivery completion.
* Production-scale telephony and multilingual support.

⸻

🗺️ Roadmap

Phase 1 — Voice Agent Prototype

* Build and test simulated delivery conversations.
* Define conversation flows, instructions, and guardrails.
* Test address clarification and basic rescheduling.

Phase 2 — Context and Workflow

* Structure customer delivery preferences.
* Retrieve relevant context for each conversation.
* Log call outcomes and unresolved exceptions.
* Build repeatable evaluation scenarios.

Phase 3 — Telephony Integration

* Explore real phone-call integration.
* Identify and handle delivery calls.
* Support appropriate fallbacks when the agent cannot resolve a request.
* Test end-to-end behaviour.

⸻

📊 Success Criteria

The MVP should demonstrate that Kallie can:

* Communicate customer instructions accurately.
* Resolve routine delivery questions without inventing information.
* Maintain context across follow-up questions.
* Recognise uncertainty and escalate appropriately.
* Record clear outcomes for each interaction.

The longer-term product goal is to reduce customer interruptions while improving the likelihood of successful doorstep deliveries.

⸻

🎥 Demo

Coming soon: A walkthrough of the working voice agent, including delivery confirmation, address clarification, and exception handling.

⸻

👩‍💻 About This Project

Kallie is an independent AI product project exploring the design and evaluation of voice agents for real-world coordination tasks.

The project focuses on the product decisions behind reliable AI behaviour: context management, guardrails, evaluation, and graceful failure handling.

Product vision: Make delivery coordination invisible, so customers can focus on their day instead of managing delivery calls.
