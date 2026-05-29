---
tags:
  - entity
relations:
  belongs_to:
    - "[[Task]]"
    - "[[Tag]]"
---

Join entity that materializes the many-to-many relationship between [[Task]] and [[Tag]]. It exists only to carry the pair (plus when the tag was applied) and has no independent domain meaning — users never see a `TaskTag` directly in the UI.

## Fields

| Field      | Type     | Notes                          |
| ---------- | -------- | ------------------------------ |
| task_id    | UUID     | FK -> [[Task]]                 |
| tag_id     | UUID     | FK -> [[Tag]]                  |
| created_at | datetime | When the tag was applied       |

## Invariants

- Composite primary key `(task_id, tag_id)` — a tag can only be applied to a given task once.
