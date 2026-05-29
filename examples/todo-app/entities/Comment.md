---
tags:
  - entity
relations:
  belongs_to:
    - "[[Task]]"
    - "[[User]]"
---

A note authored by a user against a specific [[Task]], used for context, status updates, or collaboration between people working the same task. Comments are markdown and soft-delete to preserve thread history when one is removed.

## Fields

| Field      | Type      | Notes          |
| ---------- | --------- | -------------- |
| id         | UUID      | Primary key    |
| task_id    | UUID      | FK -> [[Task]] |
| author_id  | UUID      | FK -> [[User]] |
| body       | string    | Markdown       |
| created_at | datetime  |                |
| updated_at | datetime  |                |
| deleted_at | datetime? | Soft delete    |

## Relationship notes

- The `User` relationship is the author.
