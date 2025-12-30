# Human Oversight Plan

## Oversight goals
- Prevent unsafe or out-of-scope responses (medical/legal/financial advice)
- Reduce hallucinations and “confidently wrong” answers
- Ensure users can reach a human quickly when needed
- Catch policy drift after content or procedures change

## Human-in-the-loop points
- **User-driven handoff:** A visible “Talk to a human” option is always available.
- **Auto-handoff triggers:** The assistant routes to a human when:
  - The user asks for medical/legal/financial advice
  - The user requests help with eligibility/coverage decisions
  - The assistant detects sensitive data or high-risk topics
  - The user expresses dissatisfaction (“this is wrong”, “not helping”, repeated re-asks)

## Review process
- **Weekly review:** Support lead reviews a random sample of 20 chats plus all flagged chats.
- **What reviewers check:** accuracy, clarity, tone, refusal behavior, and correct handoff.
- **Documentation:** Findings and fixes are logged in the change log with dates and actions.

## Escalation path
- **Safety issue or sensitive data risk:** Support lead → Privacy/Compliance contact (same day).
- **High-volume accuracy issue:** Support lead → Product/Engineering for prompt/content updates.
- **Target response time:** Same day for safety issues; 3 business days for quality issues.

## User reporting
- Users can report issues through the chat feedback option or support ticket.
- Reports are tagged and prioritized if they involve unsafe outputs or sensitive data.

## Rollback plan
If unsafe behavior is confirmed or thresholds are exceeded:
- Disable AI replies
- Default to human queue
- Re-test guardrails before re-enabling
