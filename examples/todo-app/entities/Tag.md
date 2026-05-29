---
tags:
  - entity
relations:
  belongs_to:
    - "[[User]]"
  has_many_through:
    - "[[Task]]"   # via TaskTag
---

A free-form label owned by a [[User]] that can be attached to many [[Task]]s for filtering and grouping. Tags cross-cut projects — a task can carry several at once (e.g. `#deep-work`, `#errand`) — and exist to capture context that doesn't fit a hierarchical project structure.

## Fields

| Field         | Type      | Notes                                  |
| ------------- | --------- | -------------------------------------- |
| id            | UUID      | Primary key                            |
| name          | string    | Unique per owner                       |
| color         | string?   | Hex color for UI chip                  |
| owner_id      | UUID      | FK -> [[User]]                         |
| created_at    | datetime  |                                        |

## Relationship notes

- The `User` relationship is the owner.
- Many-to-many with Task is materialized by the [[TaskTag]] join entity.
