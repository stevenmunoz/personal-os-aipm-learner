# Knowledge

Store reference documents, research, specs, meeting notes, and any persistent information that your tasks might need.

> This directory is gitignored—your notes stay private and local.

---

## Folder Structure

```
Knowledge/
├── Meetings/           # Processed meeting notes (structured summaries)
├── Transcripts/        # Raw meeting transcripts from Granola
├── Specs/              # Project specs and briefs
├── Research/           # Research notes and analysis
├── Process/            # Process docs, runbooks, checklists
└── References/         # Links, contacts, etc.
```

## What Goes Where

| Folder | Purpose | Examples |
|--------|---------|----------|
| `Meetings/` | Structured meeting summaries with decisions and action items | Product sync notes, stakeholder meetings, team planning |
| `Transcripts/` | Raw meeting transcripts synced from Granola | Auto-synced meeting recordings |
| `Specs/` | Project requirements and feature specifications | Feature briefs, technical specs, PRDs |
| `Research/` | Analysis and findings | Market research, technical investigations |
| `Process/` | How-to guides and operational docs | Runbooks, checklists, SOPs |
| `References/` | Quick reference materials | Links, contacts, credentials (encrypted) |

---

## Linking from Tasks

Reference knowledge docs in your task files:

```yaml
resource_refs:
  - Knowledge/project-spec.md
  - Knowledge/meeting-notes-2024-01-15.md
```

See [`examples/example_files/example_knowledge.md`](../examples/example_files/example_knowledge.md) for a template.
