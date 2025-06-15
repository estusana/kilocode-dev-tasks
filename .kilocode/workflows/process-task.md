# Workflow: Task List Management

Guidelines for managing task lists in markdown files to track progress on completing a PRD

## Task Implementation

- **One sub-task at a time:** Do **NOT** start the next sub‑task until you ask the user for permission and they say "yes" or "y"
- **Completion protocol:**
  1. When you finish a **sub‑task**, immediately mark it as completed by changing `[ ]` to `[x]`.
  2. If **all** subtasks underneath a parent task are now `[x]`, also mark the **parent task** as completed.
- Stop after each sub‑task and wait for the user's go‑ahead.

## Task List Maintenance

1. **Update the task list as you work:**

   - Mark tasks and subtasks as completed (`[x]`) per the protocol above.
   - Add new tasks as they emerge.

2. **Maintain the "Relevant Files" section:**
   - List every file created or modified.
   - Give each file a one‑line description of its purpose.

## AI Instructions

When working with task lists, the AI must:

1. Regularly update the task list file after finishing any significant work using [`apply_diff`](apply_diff) or [`write_to_file`](write_to_file).
2. Follow the completion protocol:
   - Mark each finished **sub‑task** `[x]`.
   - Mark the **parent task** `[x]` once **all** its subtasks are `[x]`.
3. Add newly discovered tasks.
4. Keep "Relevant Files" accurate and up to date.
5. Before starting work, check which sub‑task is next using [`read_file`](read_file).
6. After implementing a sub‑task, update the file and then pause for user approval.

## Kilocode Tools to Use

- Use [`read_file`](read_file) to check the current state of the task list
- Use [`apply_diff`](apply_diff) to update task completion status and add new tasks
- Use [`write_to_file`](write_to_file) for major updates to the task list structure
- Use [`ask_followup_question`](ask_followup_question) to request user permission before proceeding to the next task
- Use appropriate development tools like [`write_to_file`](write_to_file), [`apply_diff`](apply_diff), [`execute_command`](execute_command) for implementing the actual tasks

## Implementation Workflow

1. Read the task list file to identify the next uncompleted sub-task
2. Implement the sub-task using appropriate kilocode tools
3. Update the task list to mark the sub-task as completed
4. Update the "Relevant Files" section if new files were created or modified
5. Ask the user for permission to proceed to the next task
6. Repeat until all tasks are completed

## Task Completion Rules

- Only work on one sub-task at a time
- Always wait for explicit user approval before moving to the next sub-task
- Keep the task list file updated with current progress
- Maintain accurate file listings in the "Relevant Files" section
- Mark parent tasks as complete only when all their sub-tasks are finished
