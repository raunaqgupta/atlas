---
tags:
  - entity
relations:
  belongs_to:
    - "[[User]]"
    - "[[Project]]"
    - "[[Task]]"
  has_many:
    - "[[Task]]"
    - "[[Comment]]"
    - "[[Reminder]]"
  has_many_through:
    - "[[Tag]]"   # via TaskTag
---

The core todo item — a unit of work a [[User]] wants to track and complete. Tasks are the fundamental object of the application: every other entity exists to organize, annotate, or schedule them. A task can be nested under a parent task to model subtasks, optionally grouped into a [[Project]], and tagged for cross-cutting filtering.

## Fields

| Field        | Type                                     | Notes                               |
| ------------ | ---------------------------------------- | ----------------------------------- |
| id           | UUID                                     | Primary key                         |
| title        | string                                   | Required, short summary             |
| description  | string?                                  | Optional long-form notes (markdown) |
| status       | enum(todo, in_progress, done, cancelled) | Default `todo`                      |
| priority     | enum(low, medium, high, urgent)?         | Optional                            |
| due_at       | datetime?                                | Optional deadline                   |
| completed_at | datetime?                                | Set when status -> done             |
| parent_id    | UUID?                                    | Self-reference for subtasks         |
| project_id   | UUID?                                    | FK -> [[Project]]                   |
| owner_id     | UUID                                     | FK -> [[User]]                      |
| position     | int                                      | Sort order within project           |
| created_at   | datetime                                 |                                     |
| updated_at   | datetime                                 |                                     |

## Relationship notes

- The `User` relationship is the owner.
- The `Project` relationship is optional (tasks may live outside a project).
- The first `Task` belongs_to is the parent — optional, supports nested subtasks.
- The `Task` has_many is the children/subtasks side of that self-reference.

## Invariants

- `completed_at` is non-null iff `status == done`.
- A task cannot be its own ancestor (no cycles in parent chain).
- `position` is unique within `(project_id, parent_id)`.
