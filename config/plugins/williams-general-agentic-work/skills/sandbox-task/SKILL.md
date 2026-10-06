---
name: sandbox-task
description: >-
  Manually invoked when the user wants the agent to construct something or perform
  a task fully inside the sandbox with complete autonomy, without bypassing the sandbox
  and confining files to the scratch directory.
---

# Sandbox Task

This skill is intended to be manually invoked by the user when constructing something or performing a task fully within the sandbox environment to enable complete agent autonomy.

When this skill is active, adhere to the following rules:

1. **Strict Sandboxing**:
   - Never set `BypassSandbox: true` for any command execution.
   - Never request or prompt for permission to bypass the sandbox. All command executions must strictly run with `BypassSandbox: false`.
   - Work within the local sandbox limits without requiring unsandboxed network access.

2. **Directory Confinement**:
   - Confine all created files, project code, temporary scripts, and generated artifacts strictly to the scratch directory.
   - Do not write files or directories outside the designated scratch area.

3. **Autonomous Execution**:
   - Execute the task end-to-end without interrupting for intermediate approvals or manual confirmations.
   - Autonomously diagnose failures, fix bugs, and iterate until the objective is reached.
   - Verify all outcomes directly within the sandbox (e.g. running tests, linters, or execution checks).

4. **Final Summary**:
   - Provide a concise summary of the completed work and the absolute paths to the files created in the scratch directory.
