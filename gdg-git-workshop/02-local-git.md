# Part 2: Local Git - The Daily Grind (45 mins)

**Focus:** Hands-on terminal work. Walking through the standard solo developer workflow.

## 1. Setup and Initialization

### Who are you?
Before you start saving changes, Git needs to know who is making them. This information is attached to every commit you make.

Open your terminal and run these commands (replace with your actual name and the email you used for GitHub):
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### Creating a Repository
Let's create a new project.
```bash
mkdir my-awesome-project
cd my-awesome-project
```

Now, turn this normal folder into a Git repository:
```bash
git init
```
**What just happened?** Git created a hidden folder called `.git`. This folder is the "brain" of your repository. It stores all the history, configurations, and branches. If you delete the `.git` folder, you delete the history, and it becomes a normal folder again.

---

## 2. The Core Workflow: Status, Add, Commit

This is the loop you will perform dozens of times a day.

### `git status`: Your Best Friend
Always check your status. It tells you what branch you are on, what files are modified, and what is in the Staging Area.
```bash
git status
```

### Making Changes and Staging (`git add`)
Let's create a file:
```bash
echo "Hello Git World" > index.html
git status
```
Git sees `index.html` as an "Untracked file". Let's move it to the Staging Area (the loading dock).

```bash
git add index.html
# OR, to add all changes in the current directory:
# git add .
```
Run `git status` again. The file is now in green, ready to be committed!

### Saving the Snapshot (`git commit`)
Now, let's take a permanent snapshot and save it to the Repository.

```bash
git commit -m "Create initial HTML file"
```

**Pro-Tip for Commit Messages:**
Use the imperative mood, as if you are giving a command to the codebase.
*   **Good:** `Add login button`, `Fix header alignment`, `Refactor user authentication`.
*   **Bad:** `Added login button`, `Fixing header`, `stuff`, `I updated the files`.
A good rule of thumb: "If applied, this commit will [your commit message]".

### Viewing History (`git log`)
To see the timeline of your project:
```bash
git log
# For a more compact view:
git log --oneline
```

---

## 3. Branching: Safe Experimentation

**Why Branch?**
Imagine you have a working website, and you want to build a crazy new "Dark Mode" feature. You don't want to break the live site while you work on it. Branches allow you to create an isolated, parallel universe of your code. You can work there safely, and only merge it back when it's perfect.

### Managing Branches
List all your branches (the one with the `*` is active):
```bash
git branch
```

Create a new branch for our feature:
```bash
git branch feature/dark-mode
```

Move to that branch:
```bash
git checkout feature/dark-mode
# Or in newer Git versions:
git switch feature/dark-mode
```

**The Ultimate Shortcut:** Create AND switch in one command!
```bash
git checkout -b feature/awesome-header
```

---

## 4. Merging: Bringing it all together

Let's say you finished "Dark Mode" and committed those changes on your `feature/dark-mode` branch. Now, you want to bring those changes back into your main codebase (usually called `main` or `master`).

First, switch back to the receiving branch (`main`):
```bash
git checkout main
```

Now, pull the changes in from the feature branch:
```bash
git merge feature/dark-mode
```

### The Dreaded Merge Conflict
**What causes it?** Two people (or you, on two different branches) edited the *exact same line* in the *exact same file*. Git doesn't know whose change is correct, so it stops the merge and asks for human help.

When a conflict happens, Git will mark the file. If you open it in your editor, it will look like this:

```html
<<<<<<< HEAD
<h1>Welcome to my light mode site</h1>
=======
<h1 class="dark">Welcome to the dark side</h1>
>>>>>>> feature/dark-mode
```

*   `<<<<<<< HEAD`: Shows what is currently on your active branch (e.g., `main`).
*   `=======`: The divider.
*   `>>>>>>> feature/dark-mode`: Shows the incoming changes from the branch you are trying to merge.

**How to resolve it:**
1.  Open the file in your code editor (VS Code makes this very easy with buttons to "Accept Current", "Accept Incoming", or "Accept Both").
2.  Manually edit the code to look exactly how you want the final version to be. **Delete all the Git markers (`<<<<<<<`, `=======`, `>>>>>>>`).**
3.  Save the file.
4.  Stage the resolved file: `git add <file>`
5.  Finalize the merge: `git commit -m "Resolve merge conflict in index.html"`

---
*Next up, let's take this online in [Part 3: GitHub & Collaboration](03-github-collaboration.md).*
