---
name: skill-creation
description: Guidelines and structural rules for creating new skills.
---

# Skill Creation

This guide defines the required layout, formatting, and conventions when creating new skills.

- **Title:** The skill must begin with a single top-level heading (`# <Title>`) reflecting the skill name.
- **Introduction:** Directly underneath the title, include exactly one paragraph describing the purpose and scope of the skill without any intermediate section headers.
- **Bullet point formatting:** Format all rules and instructions as bullet points where each index before the colon is bolded (`- **Index:** Description`).
- **Examples section:** Only include examples if explicitly requested by the user; omit examples entirely if no explicit request was made.
- **File structure:** Place each skill inside its own directory named after the skill, containing a `SKILL.md` file with YAML frontmatter specifying `name` and `description`.
