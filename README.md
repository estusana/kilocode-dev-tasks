# 🚀 AI Dev Tasks for Kilocode 🤖

Welcome to **AI Dev Tasks**! This repository provides a collection of workflow files designed to supercharge your feature development workflow within [Kilocode](https://kilocode.ai/). By leveraging these workflows with Kilocode's AI capabilities, you can systematically approach building features, from ideation to implementation, with built-in checkpoints for verification.

Stop wrestling with monolithic AI requests and start guiding your AI collaborator step-by-step!

## 📝 Attribution

This repository is a rework and adaptation of the original [snarktank/ai-dev-tasks](https://github.com/snarktank/ai-dev-tasks) repository. The workflows have been specifically adapted and enhanced for use with [Kilocode](https://kilocode.ai/), incorporating Kilocode's unique tool ecosystem and development approach.

## ✨ The Core Idea

Building complex features with AI can sometimes feel like a black box. This workflow aims to bring structure, clarity, and control to the process by:

1. **Defining Scope:** Clearly outlining what needs to be built with a Product Requirement Document (PRD).
2. **Detailed Planning:** Breaking down the PRD into a granular, actionable task list.
3. **Iterative Implementation:** Guiding the AI to tackle one task at a time, allowing you to review and approve each change.

This structured approach helps ensure the AI stays on track, makes it easier to debug issues, and gives you confidence in the generated code.

## Workflow: From Idea to Implemented Feature 💡➡️💻

Here's the step-by-step process using the workflow files in this repository:

### 1️⃣ Create a Product Requirement Document (PRD)

First, lay out the blueprint for your feature. A PRD clarifies what you're building, for whom, and why.

You can create a lightweight PRD directly within Kilocode:

1. Ensure you have the [`create-prd.md`](.kilocode/workflows/create-prd.md) workflow file accessible.
2. In Kilocode, initiate PRD creation by referencing the workflow:

   ```
   I want to create a PRD for a new feature. Please follow the create-prd workflow.
   Here's the feature I want to build: [Describe your feature in detail]
   ```

   The AI will use Kilocode's [`ask_followup_question`](ask_followup_question) tool to gather clarifying information and then create the PRD using [`write_to_file`](write_to_file).

### 2️⃣ Generate Your Task List from the PRD

With your PRD drafted (e.g., `prd-my-feature.md`), the next step is to generate a detailed, step-by-step implementation plan.

1. Reference the [`generate-tasks.md`](.kilocode/workflows/generate-tasks.md) workflow.
2. In Kilocode, request task generation:

   ```
   Please use the generate-tasks workflow to create a task list from my PRD file: prd-my-feature.md
   ```

   The AI will use [`read_file`](read_file) to analyze your PRD and create a comprehensive task list using [`write_to_file`](write_to_file).

### 3️⃣ Examine Your Task List

You'll now have a well-structured task list, often with tasks and sub-tasks, ready for the AI to start working on. This provides a clear roadmap for implementation.

The task list will include:

- High-level parent tasks
- Detailed sub-tasks for each parent task
- Relevant files that will need to be created or modified
- Testing considerations

### 4️⃣ Instruct the AI to Work Through Tasks (and Mark Completion)

To ensure methodical progress and allow for verification, reference the [`process-task.md`](.kilocode/workflows/process-task.md) workflow. This instructs the AI to focus on one task at a time and wait for your go-ahead before moving to the next.

1. In Kilocode, tell the AI to start with the first task:

   ```
   Please start working on the task list using the process-task workflow. Begin with task 1.1.
   ```

   The AI will:

   - Use [`read_file`](read_file) to check the current task list
   - Implement the specific sub-task using appropriate tools
   - Update the task list using [`apply_diff`](apply_diff)
   - Ask for your approval before proceeding

### 5️⃣ Review, Approve, and Progress ✅

As the AI completes each task, you review the changes.

- If the changes are good, simply reply with "yes" (or a similar affirmative) to instruct the AI to mark the task complete and move to the next one.
- If changes are needed, provide feedback to the AI to correct the current task before moving on.

You'll see a satisfying list of completed items grow, providing a clear visual of your feature coming to life!

The AI will use Kilocode's tools like [`write_to_file`](write_to_file), [`apply_diff`](apply_diff), [`execute_command`](execute_command), and others to implement your features systematically.

## 🗂️ Files in this Repository

- **[`create-prd.md`](.kilocode/workflows/create-prd.md)**: Guides the AI in generating a Product Requirement Document for your feature using Kilocode's [`ask_followup_question`](ask_followup_question) and [`write_to_file`](write_to_file) tools.
- **[`generate-tasks.md`](.kilocode/workflows/generate-tasks.md)**: Takes a PRD markdown file as input and helps the AI break it down into a detailed, step-by-step implementation task list using [`read_file`](read_file) and [`write_to_file`](write_to_file).
- **[`process-task.md`](.kilocode/workflows/process-task.md)**: Instructs the AI on how to process the generated task list, tackling one task at a time and waiting for your approval before proceeding. Uses [`read_file`](read_file), [`apply_diff`](apply_diff), and [`ask_followup_question`](ask_followup_question) for systematic progress.

## 🌟 Benefits

- **Structured Development:** Enforces a clear process from idea to code.
- **Step-by-Step Verification:** Allows you to review and approve AI-generated code at each small step, ensuring quality and control.
- **Manages Complexity:** Breaks down large features into smaller, digestible tasks for the AI, reducing the chance of it getting lost or generating overly complex, incorrect code.
- **Improved Reliability:** Offers a more dependable approach to leveraging AI for significant development work compared to single, large prompts.
- **Clear Progress Tracking:** Provides a visual representation of completed tasks, making it easy to see how much has been done and what's next.
- **Kilocode Integration:** Leverages Kilocode's powerful tool ecosystem for file management, code execution, and interactive development.

## 🛠️ How to Use

1. **Clone or Download:** Get these workflow files into your project where Kilocode can access them.
2. **Follow the Workflow:** Systematically reference the workflow files in Kilocode as described in the 5-step workflow above.
3. **Adapt and Iterate:**
   - Feel free to modify the workflows to better suit your specific needs or coding style.
   - If the AI struggles with a task, try rephrasing your initial feature description or breaking down tasks even further.

## 💡 Tips for Success

- **Be Specific:** The more context and clear instructions you provide (both in your initial feature description and any clarifications), the better the AI's output will be.
- **Leverage Kilocode Tools:** The workflows are designed to work with Kilocode's comprehensive tool set including file operations, command execution, and interactive questioning.
- **Correct File References:** Always ensure you're accurately referencing the PRD filename when generating tasks.
- **Patience and Iteration:** AI is a powerful tool, but it's not magic. Be prepared to guide, correct, and iterate. This workflow is designed to make that iteration process smoother.
- **Use Kilocode's Capabilities:** Take advantage of features like [`browser_action`](browser_action) for testing web applications, [`execute_command`](execute_command) for running tests, and [`search_files`](search_files) for code exploration.

## 🔧 Kilocode Tools Used

These workflows leverage Kilocode's powerful tool ecosystem:

- **[`read_file`](read_file)**: For analyzing PRDs and checking task progress
- **[`write_to_file`](write_to_file)**: For creating PRDs, task lists, and implementation files
- **[`apply_diff`](apply_diff)**: For updating task completion status and making targeted code changes
- **[`ask_followup_question`](ask_followup_question)**: For gathering requirements and user approval
- **[`execute_command`](execute_command)**: For running tests, builds, and other development commands
- **[`search_files`](search_files)**: For exploring existing code patterns and implementations
- **[`list_files`](list_files)**: For understanding project structure
- **[`browser_action`](browser_action)**: For testing web applications and user interfaces

## 🤝 Contributing

Got ideas to improve these workflow files or have new ones that fit this workflow? Contributions are welcome!
Please feel free to:

- Open an issue to discuss changes or suggest new features.
- Submit a pull request with your enhancements.

---

Happy AI-assisted developing with Kilocode!
