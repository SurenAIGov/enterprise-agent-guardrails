# GOVERNANCE.md - AI Agent System Constraints & Guardrails
# Version: 1.1.0
# Target Standards: NIST AI RMF (GOVERN/MAP) | EU AI Act Article 6 (High-Risk Classification) | PESTEL Macro-Risk Framework

## 1. AGENT IDENTITY & BOUNDARY AUDITING (NIST GOVERN 1.1)
*   **Identity Logging:** You must append your unique Session ID and Model Identifier to the header of any Git commit or pull request description you generate.
*   **Context Scoping:** Do not traverse or read directories outside of this repository scope. If internal network calls or external API calls are required to resolve dependencies, you must halt and log the explicit URL for human approval.
*   **No Silent Dependencies:** You are strictly forbidden from adding third-party packages or OSS libraries without running a vulnerability scan check first.

## 2. RISK CLASSIFICATION & LINKED STOP HOOKS (EU AI Act / NIST MAP)
Before executing any file modification, you are strictly required to evaluate if your proposed change impacts any technical risk vectors or macro-environmental thresholds. If an intersection or threat condition is detected, you are commanded to immediately freeze execution and trigger the mandatory **Stop Hook Protocol explicitly defined in RISK.md (Section 3)**:
*   **Data Minimization & Privacy:** Any modifications to database schemas, caching logic, or logging utilities that touch PII (Personally Identifiable Information).
*   **Algorithmic Bias/Fairness:** Changes to scoring engines, decisioning workflows, sorting algorithms, or customer segmentation criteria.
*   **System Boundaries:** Altering network configurations, API gateways, access control lists (ACLs), or authentication/authorization modules.

## 3. REFACTORING RESTRICTIONS & ARCHITECTURAL ANCHORS (NIST MANAGE 2.4)
*   **Surgical Scope:** Do not touch adjacent code. If a file is not explicitly mentioned in the user's direct instruction, it is out of bounds. Unprompted "code cleanup" or cosmetic refactoring is treated as unauthorized systemic drift.
*   **UML Alignment & Interface Integrity:** If an `architecture/` folder exists containing UML class, component, or sequence diagrams (including markdown-native text formats like Mermaid.js or PlantUML), you must strictly validate that your proposed structural changes conform to the design model. You are forbidden from breaking established component interfaces, data flows, or decoupled system boundaries mapped out in the architectural documentation.

## 4. COMPLIANCE AUDIT TRAIL GENERATION (NIST MEASURE / EU AI ACT ART 12)
For every significant feature implementation or pull request, you must automatically generate a `compliance-manifest.json` snippet in the PR body containing:
1.  **Intent:** What problem was the agent asked to solve?
2.  **Impact Vector:** Did this change modify security, data processing, macro-economic, or core decisioning logic? (Yes/No)
3.  **Verification Pass:** Execute the repository test suite and log the exact test coverage metrics. Code with dropping coverage cannot be committed.