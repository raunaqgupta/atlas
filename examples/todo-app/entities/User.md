---
tags:
  - entity
relations:
  has_many:
    - "[[Task]]"
    - "[[Project]]"
    - "[[Tag]]"
    - "[[Comment]]"
---

An authenticated account representing a person who uses the todo app. Users own the [[Task]]s, [[Project]]s, and [[Tag]]s they create, author [[Comment]]s on tasks, and receive [[Reminder]]s scheduled against their timezone.

## Fields

| Field         | Type      | Notes                                  |
| ------------- | --------- | -------------------------------------- |
| id            | UUID      | Primary key                            |
| email         | string    | Unique, used for login                 |
| name          | string    | Display name                           |
| avatar_url    | string?   | Optional profile image                 |
| timezone      | string    | IANA tz, drives reminder scheduling    |
| created_at    | datetime  |                                        |
| updated_at    | datetime  |                                        |

## Relationship notes

- Owns Tasks, Projects, and Tags.
- Authors Comments.
