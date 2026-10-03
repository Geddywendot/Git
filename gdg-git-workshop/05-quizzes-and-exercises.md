# Part 5: Practical Exercises & Quizzes

Test your understanding of the concepts covered in the workshop.

## Section A: Multiple Choice Quiz

**1. What is the primary difference between Git and GitHub?**
*   A) Git is for Mac, GitHub is for Windows.
*   B) Git is the local software that tracks changes; GitHub is a cloud platform for hosting Git repositories.
*   C) Git is for small projects; GitHub is for enterprise projects.
*   D) There is no difference; they are different names for the same thing.

**2. Which Git state acts as a "drafting space" where you prepare files before saving them permanently?**
*   A) Working Directory
*   B) Commit History
*   C) The Staging Area (Index)
*   D) The `.git` folder

**3. What command is used to move changes from the Working Directory to the Staging Area?**
*   A) `git commit`
*   B) `git push`
*   C) `git stage`
*   D) `git add`

**4. You just created a new file called `styles.css`. What will `git status` say about this file?**
*   A) Staged for commit
*   B) Untracked file
*   C) Modified file
*   D) Ignored file

**5. What is the purpose of the `git checkout -b <branch-name>` command?**
*   A) Deletes a branch and creates a new one.
*   B) Creates a new branch but stays on the current one.
*   C) Switches to an existing branch.
*   D) Creates a new branch and immediately switches to it.

**6. You are collaborating on a team. A teammate tells you they just pushed a fix to the `main` branch on GitHub. What command should you run to get that fix onto your local machine?**
*   A) `git fetch`
*   B) `git pull`
*   C) `git merge`
*   D) `git clone`

**7. You want to make sure your API keys inside `.env` are NEVER uploaded to GitHub. What should you do?**
*   A) Add the file to `.gitignore`.
*   B) Never run `git add .`.
*   C) Keep the file in a different folder on your computer.
*   D) Delete the file before pushing.

**8. You committed some code locally, but realized you made a typo in the commit message. You haven't pushed yet. What is the best way to fix this?**
*   A) `git reset --hard`
*   B) Create a new commit explaining the typo.
*   C) `git commit --amend`
*   D) `git revert`

---

## Section B: Practical Terminal Scenarios

Open your terminal and try to complete these challenges without looking at the cheat sheet!

**Scenario 1: The Basics**
1.  Create a new folder called `git-practice` and navigate into it.
2.  Initialize a new Git repository.
3.  Create a file called `bio.txt` and write your name in it.
4.  Stage the file.
5.  Commit the file with the message "Add personal bio".

**Scenario 2: Branching Out**
1.  (Continuing from Scenario 1) Create a new branch called `feature/hobbies`.
2.  Switch to that new branch.
3.  Add a new line to `bio.txt` listing your favorite hobby.
4.  Stage and commit this change with a descriptive message.
5.  Switch back to the `main` (or `master`) branch.
6.  Look at `bio.txt` (using `cat bio.txt` or opening in an editor). Notice your hobby is gone!
7.  Merge the `feature/hobbies` branch into `main`.

**Scenario 3: The Stash (Advanced)**
1.  (Continuing from Scenario 2) Ensure you are on the `main` branch.
2.  Open `bio.txt` and start adding your favorite food. *Do not commit or stage this change.*
3.  Oh no! You realize this change belongs on a new branch, not `main`.
4.  Use `git stash` to hide your work.
5.  Create and switch to a new branch called `feature/food`.
6.  Use `git stash pop` to bring your work back.
7.  Now stage and commit the change on the correct branch.

---
### Quiz Answers
*(Don't peek until you've tried!)*
<details>
<summary>Click here to reveal answers</summary>

1.  **B** (Git is local tool; GitHub is cloud host)
2.  **C** (Staging Area)
3.  **D** (`git add`)
4.  **B** (Untracked file)
5.  **D** (Create and switch in one step)
6.  **B** (`git pull` fetches and merges)
7.  **A** (Add to `.gitignore`)
8.  **C** (`git commit --amend`)
</details>

---
**Congratulations on completing the GDG Git & GitHub Workshop!**
**As a bonus work, after completing your assignment try cloning or forking this repository and create a pull request**
