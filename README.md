<p align="center">
  <h1 align="center">🧠 NexusMind-360</h1>
  <p align="center"><strong>Ambient Multi-Agent Swarm Intelligence for Real-Time Customer Lifecycle Orchestration</strong></p>
  <p align="center">
    <a href="#architecture">Architecture</a> •
    <a href="#quickstart">Quickstart</a> •
    <a href="#features">Features</a> •
    <a href="#project-structure">Structure</a> •
    <a href="#demo">Demo</a>
  </p>
</p>

---

## 🚀 Overview

**NexusMind-360** is an event-driven, multi-agent system that continuously monitors streaming customer data across banking channels — payments, trading, KYC, support tickets, and web behavior — to detect emerging life-phase transitions and execute intelligent, safe interventions in real time.

Built on the **ACT-TREE 360** architecture (*Actor-Critic Blackboard Swarm with Dynamic Life-Phase Hypothesis Trees*), it goes beyond passive CRM dashboards by deploying autonomous swarm agents that reason, debate, and act on behalf of relationship managers.

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🌊 **Real-Time Stream Processing** | Ingests multi-source event logs (card payments, ACH/wire, core banking, trading, support logs, web events) in event-time order |
| 🐝 **Swarm Agent Architecture** | Specialized agents (Transaction, Usage, Support, KYC, Synthesis, Action) collaboratively analyze customer behavior |
| 🎯 **Bayesian Hypothesis Trees** | Maintains probabilistic belief trees over customer life states with red-herring suppression |
| ⚔️ **Actor-Critic Debate Engine** | Adversarial debate between Actor (proposer) and Critic (auditor) agents to filter noise |
| 🛡️ **Deterministic Guardrails** | Hard-stop regex scanners for legal/AML triggers with PII tokenization |
| 🧠 **Epistemic Blackboard Memory** | Per-customer state board with exponential decay half-lives — no context pollution |
| 👤 **Human-in-the-Loop (HITL)** | Calibrated routing between auto-approved and escalated actions with confidence bands |
| 📊 **Citation-Backed Explanations** | Every decision links to exact signal events and policy nodes |

---

## 🏗️ Architecture

```
NexusMind-360
├── core/                    # Core processing engine
│   ├── agents/              # Swarm agent implementations
│   │   ├── action_agent     # Intervention action proposer
│   │   ├── debate_agent     # Actor-Critic adversarial debate
│   │   ├── kyc_agent        # KYC/identity event analyzer
│   │   ├── refiner_agent    # Hypothesis refinement
│   │   ├── support_agent    # Support ticket NLP analyzer
│   │   ├── synthesis_agent  # Cross-domain state synthesizer
│   │   ├── txn_agent        # Transaction pattern detector
│   │   └── usage_agent      # Digital behavior tracker
│   ├── engine/              # Core engine components
│   │   ├── guardrails       # Safety & compliance barriers
│   │   ├── hitl_engine      # Human-in-the-loop router
│   │   ├── memory_engine    # Memory management system
│   │   ├── nlp_engine       # NLP processing pipeline
│   │   ├── state_board      # Epistemic blackboard (per-customer)
│   │   └── stream_processor # Real-time event stream handler
│   └── schemas/             # Data models & type definitions
├── server/                  # Application server layer
│   ├── hitl/                # HITL service endpoints
│   ├── memory/              # Memory subsystems (episodic, semantic, working)
│   ├── observability/       # Audit trail & monitoring
│   └── orchestration/       # LangGraph orchestration
├── datasets/                # Customer scenario datasets
│   ├── scenario_01/         # Medical hardship detection
│   ├── scenario_02/         # Retirement transition
│   └── scenario_03/         # Business expansion signals
├── docs/                    # Documentation
│   ├── research/            # Research logs & literature review
│   ├── architecture/        # System architecture specs
│   └── reports/             # Submission reports & evaluations
├── scripts/                 # Execution scripts
│   ├── run_pipeline.py      # Main pipeline runner
│   └── evaluate_scenarios.py# Scenario evaluation scorer
└── tests/                   # Test suite
```

---

## ⚡ Quickstart

### Prerequisites
- Python 3.10+
- Docker & Docker Compose (optional, for full deployment)
- OpenAI API Key (for LLM-powered agents)

### Installation

```bash
# Clone the repository
git clone https://github.com/Sutirthdubey20005/NexusMind-360.git
cd NexusMind-360

# Install dependencies
pip install -r requirements.txt

# Set your API key
export OPENAI_API_KEY="your-key-here"
```

### Run the Pipeline

```bash
# Execute the full agentic pipeline on a scenario
python scripts/run_pipeline.py

# Evaluate scenario accuracy
python scripts/evaluate_scenarios.py
```

### Docker Deployment

```bash
docker-compose up --build
```

---

## 🎬 Demo

Running `python scripts/run_pipeline.py` launches an interactive terminal dashboard:

```
========================================================================
               NexusMind-360 STREAM PROCESSOR: scenario_01               
========================================================================
👤 Customer Profile: Marcus Vance (CUST_00042) | Segment: Standard
📦 Loaded Stream Events: 375 Seed Events | 116 Live Stream Events

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
 🕒 CHECKPOINT #3 [AS-OF TIME: 2026-03-26T00:00:00Z]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📥 Stream Influx: 43 Txns | 1 Support Logs | 31 Logins | 0 KYC Updates
🐝 Swarm Assertions Published to State Board:
   • hospital_bill_posted          : val=True    | conf=0.95
   • search_intent_hardship        : val=True    | conf=0.95
   • medical_support_ticket        : val=True    | conf=0.98
⚔️ Actor-Critic Debate: State -> medical_hardship | Conf -> high
🎯 Final Decision: support_intervention (medical_hardship_payment_plan)
🚦 HITL Checkpoint: ESCALATED

==================================================
 FINAL SCORE: 110.0 / 110.0 (100.0%)
==================================================
```

---

## 🔬 Core Concepts

### Dynamic Bayesian Life-Phase Hypothesis Trees
Maintains a probabilistic belief tree over candidate customer states across event timelines, suppressing state jumps on red herrings (e.g., tuition wires or tax refunds) until multi-domain cross-validation occurs.

### Epistemic Blackboard (`SharedStateBoard`)
Swarm agents write customer-scoped key-value assertions with exponential decay half-lives, eliminating context pollution and multi-tenant memory leakage.

### Actor-Critic Adversarial Debate
Resolves swarm agent disagreements by pairing an *Actor Agent* (state/action proposer) with an adversarial *Critic Agent* (red-herring auditor).

---

## 📄 License

This project is provided for educational and research purposes.

---

<p align="center">
  Built with 🧠 by <a href="https://github.com/Sutirthdubey20005">Sutirth Dubey</a>
</p>
