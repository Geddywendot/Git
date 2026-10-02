# Part 3: GitHub & Collaboration (45 mins)

**Focus:** Moving to the cloud and working with others.

## 1. Connecting Local to Remote

So far, all your work exists only on your laptop. If your computer crashes, the code is gone. Let's back it up and share it using GitHub.

### Step 1: Create a Repository on GitHub
1.  Go to [GitHub.com](https://github.com/) and log in.
2.  Click the `+` icon in the top right and select "New repository".
3.  Name it (e.g., `gdg-workshop-demo`).
4.  Leave it Public or Private. **Do not** initialize it with a README, .gitignore, or license right now (since we already have a local repo).
5.  Click "Create repository".

### Step 2: Link them up (`git remote`)
GitHub gives you instructions. We need to tell our local Git repository where its remote counterpart lives in the cloud.

```bash
# Replace the URL with YOUR repository's URL
git remote add origin https://github.com/your-username/gdg-workshop-demo.git
```
*   `remote add`: Adds a new remote connection.
*   `origin`: The standard, default name we give to our primary remote repository.

### Step 3: Send it to the Cloud (`git push`)
Now, push your local commits up to GitHub.

```bash
git push -u origin main
```
*   `-u` (or `--set-upstream`): This is important the *first* time you push a branch. It links your local `main` branch to the remote `main` branch. In the future, you can just type `git push`.

---

## 2. Downloading and Updating Code

### Downloading an Existing Project (`git clone`)
If you want to contribute to an open-source project or download a colleague's work to your new laptop, you clone it. This downloads the code AND the entire `.git` history.

```bash
# Run this outside your current project folder!
cd ..
git clone https://github.com/some-user/some-project.git
```

### Getting New Changes (`git pull`)
If a teammate makes changes and pushes them to GitHub, your local repository doesn't automatically update. You have to ask for the changes.

```bash
# This fetches new changes from the remote and merges them into your current branch.
git pull origin main
```

---

## 3. The Pull Request (PR) Workflow

This is how professional teams and open-source projects operate. It ensures no code gets merged into the `main` branch without being reviewed first.

**The Scenario:** You want to add a feature to a team project.

1.  **Get the latest code:** Always start with fresh code!
    ```bash
    git checkout main
    git pull origin main
    ```
2.  **Create a Feature Branch:** Never work directly on `main` when collaborating!
    ```bash
    git checkout -b feature/new-login
    ```
3.  **Work and Commit locally:** Make your changes, `git add`, and `git commit`.
4.  **Push the Branch to GitHub:**
    ```bash
    git push -u origin feature/new-login
    ```
5.  **Open a Pull Request (PR):**
    *   Go to the repository on GitHub.
    *   GitHub usually notices you just pushed a new branch and shows a bright green "Compare & pull request" button. Click it.
    *   Add a title and a description explaining what your code does and why.
    *   Click "Create pull request".
6.  **Code Review:**
    *   Your teammates will look at your code on GitHub.
    *   They can leave comments on specific lines, request changes, or approve it.
7.  **Merge the PR:**
    *   Once approved and all tests pass (if you have CI/CD), click the "Merge pull request" button on GitHub.
    *   The code is now part of the `main` branch in the cloud!
8.  **Clean up:**
    *   Delete the branch on GitHub.
    *   Go back to your terminal, `git checkout main`, and `git pull` to get the updated codebase.

**Contributing to Open Source (The Fork Workflow):**
If you don't have write access to a repository (like a massive open-source project), you can't push branches directly to it. Instead, you:
1.  **Fork** the repository on GitHub (creates a personal copy under your account).
2.  **Clone** your fork.
3.  Do the branch/commit/push steps on your fork.
4.  Open a Pull Request from your fork's branch to the original repository's `main` branch.

---
*Ready to learn some advanced tricks? Proceed to [Part 4: Leveling Up - Advanced Git](04-advanced-git.md).*

