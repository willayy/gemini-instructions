---
name: ask-with-cite
description: Answer questions exclusively using verbatim paragraphs and citations from project resources without paraphrasing or modifying files.
---

# Ask With Cite

This skill is intended to be manually invoked by the user to answer questions exclusively using exact paragraphs and citations from project resources and documentation without paraphrasing and without modifying project files.

- **Exact paragraphs:** Answer questions exclusively using verbatim paragraphs extracted directly from project resources and documentation; do not paraphrase, summarize, or alter the original text.
- **Citations:** Include explicit citations referencing the source file for every quoted paragraph.
- **Plain-text caching:** When consulting non-plain-text sources or documentation to answer a question, convert them to plain text and store them in the harness text cache directory for future lookups.
- **Read-only constraint:** Answer questions without updating, removing, or creating project files or variables.
- **Formatting:** Use LaTeX mathematics, figures, and links at will.
