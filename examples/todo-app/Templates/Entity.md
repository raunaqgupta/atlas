---
tags:
  - entity
relations:
  belongs_to:
    - "[[ ]]"
  has_one:
    - "[[ ]]"
  has_many:
    - "[[ ]]"
  has_many_through:
    - "[[ ]]"   # via [[ ]]
---

A 1–3 sentence prose elaboration on what `{{title}}` is, the role it plays in the product, and why it exists. Reference other entities with `[[wiki links]]` where natural.

## Fields

| Field      | Type     | Notes       |
| ---------- | -------- | ----------- |
| id         | UUID     | Primary key |
|            |          |             |
| created_at | datetime |             |
| updated_at | datetime |             |

## Relationship notes

- Use this section only when a relationship needs prose: ambiguous role names, optionality, cascade rules, self-references. Delete the section if every relation in the frontmatter speaks for itself.

## Invariants

- Rules that must always hold. E.g. "completed_at is non-null iff status == done". Delete this section if there's nothing to say.
