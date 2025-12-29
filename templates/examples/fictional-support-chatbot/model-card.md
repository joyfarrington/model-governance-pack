# Model Card

## 1) Model overview
- **Model name:** HelpDesk Routing Assistant
- **Owner/team:** Support Operations
- **Version:** v0.1
- **Last updated:** 2025-12-29
- **Model type:** LLM-based assistant (FAQ + routing)
- **Deployment:** Customer-facing chat widget with human handoff

## 2) Purpose
- **Problem it solves:** Reduce time to answer common support questions and route complex issues to humans.
- **Primary users:** Customers and support agents.
- **Expected benefits:** Faster responses for FAQs, clearer triage, lower agent load.

## 3) Training and data (high level)
- **Data sources:** Public help-center articles, internal policy/FAQ documents (approved), sanitized historical chat snippets (optional).
- **Sensitive data included?** No. The assistant is designed to avoid collecting sensitive info.
- **Data retention approach:** Logs retained for troubleshooting with redaction rules.
- **Known data constraints:** Knowledge can go stale when policies change.

## 4) Intended use
- **Allowed use cases:** FAQs, account guidance, routing to the right team, summarizing a customer issue for an agent.
- **Disallowed use cases:** Medical, legal, or financial advice; collecting sensitive personal data; final decisions on eligibility/coverage.
- **Out-of-scope:** Diagnosis, treatment guidance, or anything requiring professional judgment.

## 5) Performance and evaluation
- **Success metrics:** Resolution rate for FAQs, correct routing rate, safe-completion rate.
- **Evaluation methods:** Test set of common questions, red-team prompts for unsafe requests, weekly sampling of chats.
- **Known failure modes:** Confident wrong answers, policy drift, misunderstanding user intent.
- **Fairness checks performed:** Not applicable for routing decisions in v0.1 (revisit if used for prioritization).

## 6) Risks and mitigations
- Risk: Hallucinated answers  
  Mitigation: Link to sources, refuse when unsure, route to human  
  Residual risk: Medium

- Risk: Sensitive data collection  
  Mitigation: PII warnings, input filters, redaction in logs  
  Residual risk: Low

## 7) Human oversight
- **Where humans review/approve:** Human handoff available at all times; weekly quality review by leads.
- **Escalation path:** Safety issue → Support lead → Compliance/Privacy contact.
- **User transparency:** Clear banner: “AI assistant, may be wrong. You can request a human anytime.”

## 8) Monitoring and maintenance
- **What gets monitored:** Unsafe completions, hallucination reports, handoff rate, policy updates.
- **Alert thresholds:** Spike in “wrong answer” reports or policy change events.
- **Retraining/refresh cadence:** Monthly review of content sources; update prompts weekly if needed.
- **Rollback plan:** Disable AI responses and default to human queue.
