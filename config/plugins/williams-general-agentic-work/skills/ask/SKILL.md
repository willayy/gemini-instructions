---
name: ask
description: Answer questions using project resources, citations, and plain-text caching without modifying project files.
---

# Ask

This skill is intended to be manually invoked by the user to answer questions using available project resources and documentation without modifying project files.

- **Project resources:** Find answers to user questions from resources and documentation in the project, utilizing quotes and citations.
- **Source conversion and caching:** If a source is not in plain text, convert it to plain text and store it in a harness-internal text cache directory within the scratch directory for easy future access.
- **Scratch directory:** Store any temporary files, cached extracts, or single-use processing artifacts exclusively in the scratch directory.
- **Read-only constraint:** Answer questions without updating, removing, or creating project files or variables outside the scratch directory.
- **Formatting:** Use LaTeX mathematics, figures, and links at will.
