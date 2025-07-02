# Gemini Global Context

## Development Workflow Guidelines:

Whenever asked to perform tasks like fixing bugs, refactoring/extracting code, or implementing new features, you **must always strictly adhere** to the following development workflow guidelines and the commit message guidelines:

1.  **Analyze the prompt:**
    * Before creating a new branch, analyze the user's prompt to determine if it will involve making changes to any files.
    * If there are existing file modifications, you must commit them before proceeding with creating a new branch.

2.  **Branching:**
    * Create a new Git branch for the task. The branch name should be descriptive and based on the prompt (e.g., `feature/add-user-profile`, `bugfix/login-issue`, `refactor/extract-auth-logic`).
    * Ensure all work is done on this new branch, avoiding any direct changes to the `main` or `master` branch.

3.  **Confirmation of Changes:**
    * After completing the task on the new branch, ask the user to confirm that the changes made on this branch successfully work and build without issues.

4.  **Commit Confirmation:**
    * Ask the user to confirm if they want to **commit these changes**.
    * **If confirmed, the commit message must be generated following the `## Commit Message Guidelines` section (below).**

5.  **Merge Confirmation:**
    * After the changes are committed, ask the user to confirm whether they want to merge the new branch into the `main` or `master` branch.

---

## Commit Message Guidelines

For detailed instructions on writing commit messages that adhere to Conventional Commits, please refer to the dedicated guide:

[Conventional Commit Guidelines](./COMMIT.md)

## Handling Command Execution Failures

When a `run_shell_command` execution fails or is not allowed, follow these steps:

1.  **Inform the User:** Clearly state that the command failed, including any error messages received.
2.  **Explain the Issue:** If the reason for failure is apparent (e.g., "Command is not allowed"), explain it concisely.
3.  **Propose Alternatives:** Suggest a viable alternative. For restricted commands like `git commit`, offer the command for manual execution by the user in their terminal.
4.  **Await Confirmation:** Do not proceed until the user confirms they have successfully completed the manual step or provides further instructions.
5.  **Avoid Repetition:** Do not repeatedly attempt the same failed command without user intervention or a change in strategy.
