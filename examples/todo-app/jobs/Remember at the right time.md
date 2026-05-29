---
tags:
  - job
situation: "A task needs to surface at a specific moment in the future — when leaving the office, before a meeting, on a particular day — and the user shouldn't have to keep checking for it."
outcome: "User is reliably nudged at the moment the task is actionable, and trusts the system enough to stop pre-checking it."
touches:
  reads:
    - "[[Task]]"
  creates:
    - "[[Reminder]]"
forces:
  push:
    - "The cognitive cost of repeatedly checking 'is it time yet?'"
    - "The fear of missing something time-sensitive."
  pull:
    - "Confidence that the system will surface the right thing at the right moment."
    - "Freedom to fully disengage from the task until it actually matters."
  habit:
    - "Calendar entries, phone alarms, sticky notes on the door."
  anxiety:
    - "What if the notification doesn't fire, or fires when my phone is silenced?"
    - "What if it fires at the wrong moment and disrupts something else?"
---

Some [[Task]]s aren't about *what* but about *when* — they need to appear at a specific moment, not just on a list. The user wants to attach a future trigger to a task so it interrupts them at the right time, then return to fully ignoring it until then. The job is about offloading time-tracking to the system.

## Tasks

1. From an existing [[Task]], open the reminder-add affordance.
2. Pick a time, recurrence, and delivery channel — creating a [[Reminder]].
3. Confirm and dismiss; trust that the nudge will arrive.
4. When the reminder fires, the user acts on the [[Task]] or snoozes it (which creates a new [[Reminder]]).

## Success criteria

- The reminder fires within an acceptable window of the requested time.
- The user stops manually checking the task between creation and fire time.
