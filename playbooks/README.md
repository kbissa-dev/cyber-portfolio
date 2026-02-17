# Playbooks
This folder contains step-by-step investigation playbooks (what to check, in what order) for common SOC alerts.

## Naming Convention
Use: 'alerttype_playbook_v1.md'

## Playbook format
### Trigger
What alert / symptom starts the palybook.

### Goal
What "done" looks like (close, monitor, escalate).

### Inputs
What you need: logs, tools, access, tickets, time window.

### Steps (in order)
1. Validate the alert (is it real?)
2. Scope the impact (who/what affected)
3. Collect evidence (key events + timestamps)
4. Decide severity
5. Contain / escalate / close
6. Document clearly

### Evidence checklist
A short list of what screenshots/log lines to capture.

### Escalation criteria
When to escalate + who to notify.

### Closure notes
What must be written in the ticket before closing.
