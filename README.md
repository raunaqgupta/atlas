# Atlas

A Claude plugin for product planning in Obsidian. Atlas turns early-stage product conversations into a navigable knowledge graph — entities linked to jobs, jobs linked back to entities — before a line of code is written.

## Skills

**`entity-modeling`** — Model the core nouns of a product (User, Task, Project, etc.) as linked entity notes in an Obsidian vault. Each note describes fields, relations, and invariants. Relations use `[[wiki links]]` so the vault becomes a clickable, graph-viewable schema.

**`jtbd-modeling`** — Model the jobs users hire the product to do, using the Christensen JTBD framework: situation, outcome, the four forces (push, pull, habit, anxiety), and the entities each job touches. Jobs link to entities so the same vault holds both *what* the product is and *why* anyone would use it.

**`create-entity`** / **`create-job`** — Primitives for writing a single entity or job note. Called by the modeling skills above, or directly when adding one artifact to an existing vault.

## Usage

Install as a Claude plugin, then use naturally in conversation:

- "I want to build a habit tracker — let's model the entities."
- "What job is this product doing for the user?"
- "Add a Notification entity to the vault at ~/projects/my-app."

Atlas will propose a set, confirm with you, then write the notes.

## Example

The `examples/todo-app/` vault shows a complete entity and job model for a todo application.
