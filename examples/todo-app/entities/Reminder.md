---
tags:
  - entity
relations:
  belongs_to:
    - "[[Task]]"
    - "[[User]]"
---

A scheduled notification tied to a [[Task]] that fires at a specific time for a specific [[User]] over a chosen delivery channel. Reminders can be one-off or recurring, and they decouple "when to act" from the task's own due date so a user can be nudged ahead of a deadline.

## Fields

| Field         | Type                                     | Notes                                |
| ------------- | ---------------------------------------- | ------------------------------------ |
| id            | UUID                                     | Primary key                          |
| task_id       | UUID                                     | FK -> [[Task]]                       |
| user_id       | UUID                                     | FK -> [[User]] (who gets notified)   |
| remind_at     | datetime                                 | When to fire                         |
| channel       | enum(push, email, in_app)                | Delivery channel                     |
| recurrence    | enum(none, daily, weekly, monthly)       | Default `none`                       |
| sent_at       | datetime?                                | Null until delivered                 |
| created_at    | datetime                                 |                                      |

## Relationship notes

- The `User` relationship is the recipient (who gets notified).

## Invariants

- `remind_at` is in the future at creation time.
- If `recurrence != none`, a new Reminder is queued after `sent_at` is set.
