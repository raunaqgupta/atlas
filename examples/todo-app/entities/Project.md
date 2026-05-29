---
tags:
  - entity
relations:
  belongs_to:
    - "[[User]]"
  has_many:
    - "[[Task]]"
---

A named collection of [[Task]]s — sometimes surfaced in UI as a list or board — that lets a [[User]] organize work by goal, area of life, or context. Users can own zero or more projects, and tasks may exist outside any project.

## Fields

| Field         | Type      | Notes                                  |
| ------------- | --------- | -------------------------------------- |
| id            | UUID      | Primary key                            |
| name          | string    | Display name                           |
| description   | string?   | Optional                               |
| color         | string?   | Hex color for UI                       |
| icon          | string?   | Emoji or icon identifier               |
| owner_id      | UUID      | FK -> [[User]]                         |
| archived_at   | datetime? | Null when active                       |
| position      | int       | Sort order in sidebar                  |
| created_at    | datetime  |                                        |
| updated_at    | datetime  |                                        |

## Relationship notes

- The `User` relationship is the owner.
