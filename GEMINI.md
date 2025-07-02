# Gemini Global Context

## Development Workflow Guidelines:

Whenever asked to perform tasks like fixing bugs, refactoring/extracting code, or implementing new features, always follow these steps:

1.  **Branching:**
    * Create a new Git branch for the task. The branch name should be descriptive and based on the prompt (e.g., `feature/add-user-profile`, `bugfix/login-issue`, `refactor/extract-auth-logic`).
    * Ensure all work is done on this new branch, avoiding any direct changes to the `main` or `master` branch.

2.  **Confirmation of Changes:**
    * After completing the task on the new branch, ask the user to confirm that the changes made on this branch successfully work and build without issues.

3.  **Commit Confirmation:**
    * Ask the user to confirm if they want to **commit these changes**.
    * **If confirmed, the commit message must be generated following the `## Commit Message Guidelines` section (below).**

4.  **Merge Confirmation:**
    * After the changes are committed, ask the user to confirm whether they want to merge the new branch into the `main` or `master` branch.

---

## Commit Message Guidelines

For detailed instructions on writing commit messages that adhere to Conventional Commits, please refer to the dedicated guide:

[Conventional Commit Guidelines](./.gemini/COMMIT.md)
