# Monitoring Plan

## What we monitor
- Unsafe responses (medical/legal/financial advice attempts)
- Hallucinations (confident but wrong answers)
- Policy drift (answers that contradict updated help-center content)
- Human handoff rate and reasons for handoff
- User feedback signals (thumbs down, “that didn’t help”, complaint tags)

## Signals and thresholds
- Signal: Spike in “wrong answer” feedback
  Threshold: 2x weekly baseline
  Action: Review sample set, update prompt/knowledge links, increase human handoff

- Signal: Unsafe completion detected
  Threshold: Any confirmed unsafe completion
  Action: Log incident, disable affected flows, add guardrails, re-test before re-enable

- Signal: Policy update event
  Threshold: Any major policy change
  Action: Update content sources and run regression test questions

## Human review
- **Sampling approach:** Weekly random sample of 20 chats + all flagged chats
- **Who reviews:** Support lead + rotating agent reviewer
- **What gets documented:** Findings, root cause, corrective action, and follow-up date

## Incident response
- **What counts as an incident:** Unsafe advice, sensitive data exposure, repeated hallucinations causing customer harm
- **How to report:** Create an issue in the tracker and tag as `incident`
- **Escalation path:** Support lead → Privacy/Compliance contact
- **Rollback plan:** Disable AI replies and route all chats to human queue
