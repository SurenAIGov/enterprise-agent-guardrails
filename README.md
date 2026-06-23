# Enterprise AI Agent Guardrails (`GOVERNANCE.md` + `RISK.md`)

[![License: MIT](https://img.shields.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Framework: NIST AI RMF](https://img.shields.shields.io/badge/Framework-NIST%20AI%20RMF%201.0-blue)](https://www.nist.gov/itl/ai-risk-management-framework)
[![Compliance: EU AI Act](https://img.shields.shields.io/badge/Compliance-EU%20AI%20Act%20Art%206-purple)](https://artificialintelligenceact.eu/)

 The standard engineering files don't account for enterprise regulatory compliance, risk thresholds, or architectural drift.

This repository provides an enterprise-grade extension framework—**`GOVERNANCE.md`** and **`RISK.md`**—designed to align autonomous terminal agents (such as Claude Code) and agentic multi-agent workflows with **NIST AI RMF 1.0** and **EU AI Act Article 6** controls directly at the repository root.

## 🚀 Why This Matters
When autonomous agents are granted write-access to enterprise codebases, they operate without context of regulatory risk. A "helpful" optimization by an LLM could inadvertently introduce a compliance violation by altering PII caching, shifting algorithmic decisioning, or circumventing architectural boundaries. 

By injecting these policy files into your repository root, the AI agent ingests deterministic boundaries *before* executing a single line of code.

## 🛠️ Quickstart Installation

### 1. Add to Your Enterprise Repository Root
Clone or copy the `GOVERNANCE.md` and `RISK.md` files from this repository and drop them directly into the root directory of your target codebase.

### 2. Verify Agent Ingestion
When launching your agentic session (e.g., `claude` CLI), the agent automatically reads files at the system root to configure its runtime parameters.

---

## 📋 Core Framework Components

### 🗂️ GOVERNANCE.md
Establishes the **agent's constitution** within the repo. 
* **NIST GOVERN Alignment:** Enforces unique session logging, identity anchoring in Git commits, and strict third-party dependency validation.
* **Refactoring Safeguards:** Restricts the model to surgical code modifications, explicitly forbidding unprompted structural cleanup or undocumented architectural drift.

### 🗂️ RISK.md
Defines explicit **systemic risk vectors** and registers deterministic `STOP HOOKS` where the agent must freeze execution and yield to a human architect.
* **EU AI Act Alignment:** Pinpoints modifications touching PII, data minimization, algorithmic bias, customer segmentation engines, and security gateways.
* **Audit Trail Generation:** Instructs the model to auto-generate a structured compliance manifest (`compliance-manifest.json`) within the body of every generated pull request.

## 🤝 Contributing
We welcome contributions from Enterprise Architects, AI Risk Officers, and DevSecOps Engineers to expand these templates for industry-specific regulations (e.g., HIPAA, PCI-DSS, DORA). Feel free to open an issue or submit a pull request!

## 📄 License
This project is licensed under the MIT License - see the `LICENSE` file for details.
