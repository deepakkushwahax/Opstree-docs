
# Understanding of Commit Hooks

<div align="center">
    <img width="545" height="349" alt="image" src="https://github.com/user-attachments/assets/ecb1007e-2f05-4ca9-9123-2a38a4b79fb9" style="border-radius: 15px;" />
</div>



## Author Information

| Created by      | Created on         | Version          | Last updated On   | pre Reviewer       | L0 Reviewer     | L1 Reviewer          |    L2 Reviewer    |
|-----------------|--------------------|------------------|-------------------|--------------------|-----------------|----------------------|-------------------|
| Deepak Kushwaha  |  30-07-2025        | V 1.0            |        |  Anjali          |       |     -   |   - |
| Deepak Kushwaha  |  30-07-2025        | V 1.1            |  05-08-2025     |   Anjali     |       |     -   |   - |
| Deepak Kushwaha  |  30-07-2025        | V 2           |  07-08-2025     |        |   Priyanshu    |     -   |   - |


## Table of Contents

1. [Introduction](#introduction)
2. [Purpose of Commit Hooks](#purpose-of-commit-hooks)
3. [Types of Commit Hooks](#types-of-commit-hooks)
4. [How to Use Git Hooks](#how-to-use-git-hooks)
5. [Commands](#commands)
6. [Feature](#feature)
7. [FAQs](#faqs)
8. [Conclusion](#conclusion)
9. [Contact Information](#contact-information)
10. [References](#references)

---

## Introduction

Git commit hooks are small programs that run automatically when you make a commit in Git. They help you check your code—for example, making sure it's formatted correctly or doesn't have errors—before it gets saved. This helps keep everyone's code clean and consistent without doing everything manually.

---


## Purpose of Commit Hooks

Git commit hooks are scripts that run automatically at certain points in your Git workflow—such as before making a commit. They help improve your code and workflow by automating tasks and enforcing rules.

### Why We Use Commit Hooks

| Purpose                 | Description                                                                      |
|-------------------------|----------------------------------------------------------------------------------|
| **Keep Code Clean**     | Make sure everyone writes code that follows the same rules and style.           |
| **Save Time with Automation** | Automatically run tasks like formatting or tests before each commit.         |
| **Catch Mistakes Early**| Find issues before the code is saved, preventing future bugs or problems.       |
| **Help Teams Work Better**| Encourage consistent workflows across the team for smoother collaboration.     |



---

## Types of Commit Hooks

<img width="900" length="600" alt="Terraform" src="https://d8it4huxumps7.cloudfront.net/uploads/images/652f8091f32cc_git_hooks_06.jpg?d=2000x2000">

Git hooks come in two types: **Client-Side** and **Server-Side**. Each type helps automate different parts of the Git workflow.

### 1. Client-Side Hooks

These hooks run on the developer's local machine and are mainly used for checking code and preparing commits before they're made.

| Hook Name             | What It Does                                                                 |
|-----------------------|------------------------------------------------------------------------------|
| **pre-commit**        | Runs before a commit is created. Useful for checking code or running tests. |
| **prepare-commit-msg**| Edits or sets up the commit message before the user writes it.              |
| **commit-msg**        | Checks or changes the final commit message before saving.                   |
| **post-commit**       | Runs after a commit is made. Often used for local notifications or logging. |

---

### 2. Server-Side Hooks

These hooks run on the Git server and help enforce rules across all users who push to the repository.

| Hook Name         | What It Does                                                                     |
|-------------------|----------------------------------------------------------------------------------|
| **pre-receive**   | Runs before any changes are accepted into the repo. Used to block bad commits.  |
| **update**        | Checks each branch update before accepting it. Useful for branch-specific rules.|
| **post-receive**  | Runs after changes are accepted. Often used to trigger CI/CD tools or alerts.   |

## How to Use Git Hooks

### Setting Up Git Hooks

1. Navigate to the .git/hooks directory in your Git project.
2. Identify the hook script you want to customize (e.g., pre-commit).
3. Create or modify the script file, ensuring it is executable:

   bash
   chmod +x .git/hooks/<hook-name>
   

4. Add your desired script logic to automate tasks or enforce rules.

---

## Commands

### Basic Git Hook Commands

| Command | Description |
|---------|-------------|
| `chmod +x .git/hooks/pre-commit` | Make pre-commit hook executable |
| `git commit -m "message"` | Create a commit (triggers hooks) |
| `git push origin main` | Push changes to remote repository |
| `ls -la .git/hooks/` | List all available hooks |
| `cat .git/hooks/pre-commit` | View pre-commit hook content |

### Creating Custom Hooks

```bash
# Create a new pre-commit hook
touch .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit

# Edit the hook with your custom logic
nano .git/hooks/pre-commit
```

### Testing Hooks

```bash
# Test if hooks are working
git add .
git commit -m "test commit"
```

---

## Features

| Feature                          | Description                                                                                  |
|----------------------------------|----------------------------------------------------------------------------------------------|
| **Automation of Tasks**          | Automatically handles repetitive steps like formatting or running tests.                    |
| **Pre-Commit and Post-Commit Hooks** | Supports checks before and after commits to enforce project rules.                          |
| **Quality Control**              | Helps maintain clean, consistent code by enforcing coding standards.                        |
| **Customization**                | Easily configurable to fit the specific needs and workflows of your project.                |
| **Error Prevention**             | Catches issues early before they reach your codebase.                                       |
| **Lightweight Execution**        | Runs quickly without slowing down your development process.                                 |


---

## FAQs

### 1. Are Git commit hooks?
Git commit hooks are scripts that run automatically at specific points in the Git workflow (like before or after a commit). They help automate tasks such as code checks, formatting, and more.

### 2. Are Git hooks enabled by default?
Yes, Git includes sample hook scripts in every repository under `.git/hooks/`, but they are not active until you rename them and make them executable.

### 3. Is the difference between client-side and server-side hooks?
- **Client-side hooks** run on a developer's machine (e.g., to format code before committing).
- **Server-side hooks** run on the Git server (e.g., to reject non-compliant code pushes).

### 4. Can Git hooks be shared across a team?
Not by default. Git does not sync the `.git/hooks` folder. Tools like **Husky** or **pre-commit** help share and manage hooks in a team-friendly way.

### 5. Can I use multiple hooks at once?
Yes, you can use multiple hook scripts in your project, each serving a specific role (e.g., `pre-commit`, `commit-msg`, and `post-commit` can all coexist).

### 6. Do Git hooks affect performance?
Not significantly. Git hooks are lightweight and run locally or on the server during specific events. Poorly written scripts, however, can slow down your workflow.

---

## Conclusion

Commit hooks enhance the development process by automating checks and enforcing coding standards at the time of commits. They help catch errors early, improve overall code quality, and ensure consistent workflows across teams. By integrating commit hooks into your Git workflow, you can prevent common mistakes, save time on manual reviews, and build more reliable software.

---

## Contact Information
| **Name**           | **Email address**                         |
|--------------------|--------------------------------------------|
| Deepak Kushwaha    | [deepak.kushwaha.snaatak@mygurukulam.co](mailto:deepak.kushwaha.snaatak@mygurukulam.co) |

---


## References

| Reference                         | Link                                              |
|-----------------------------------|---------------------------------------------------|
| Git Documentation on Hooks        |[Click here](https://git-scm.com/book/ms/v2/Customizing-Git-Git-Hooks) |
| Husky                             |[Click here](https://typicode.github.io/husky/) |
| Prettier Git Hooks                |[Click here](https://medium.com/@dlyusko/how-to-set-up-a-pre-commit-hook-with-prettier-and-eslint-using-husky-3ca6a9ae7e63) |
