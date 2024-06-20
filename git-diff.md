## Git diff

`git diff <source branch or commit>..<target branch or commit>`

The `git diff` command is used to show the differences between various states in your Git repository. This command is extremely useful for understanding what changes have been made to your code or files before committing them, or for comparing different commits or branches. Here's a detailed explanation of how `git diff` works and how to use it effectively:

### Basic Usage

1. **Unstaged Changes**:
   ```sh
   git diff
   ```
   This shows the changes between the working directory and the staging area. In other words, it displays the changes you have made but not yet staged for commit.

2. **Staged Changes**:
   ```sh
   git diff --staged
   ```
   This shows the changes between the staging area and the last commit. These are the changes that are currently staged and will be included in the next commit.

### Comparing Different States

1. **Between Commits**:
   ```sh
   git diff commit1 commit2
   ```
   This shows the differences between two commits. Replace `commit1` and `commit2` with the commit hashes or references (like branch names).

2. **Between a Commit and Working Directory**:
   ```sh
   git diff commit
   ```
   This shows the differences between the specified commit and the working directory.

3. **Between Branches**:
   ```sh
   git diff branch1 branch2
   ```
   This shows the differences between two branches.

4. **Between a Branch and the Working Directory**:
   ```sh
   git diff branch
   ```
   This shows the differences between the specified branch and the working directory.

5. **Against a Remote Branch**:
   ```sh
   git diff origin/main
   ```
   This shows the differences between your working directory and the `main` branch on the remote named `origin`.

### Advanced Usage

1. **Comparing Specific Files**:
   ```sh
   git diff commit1 commit2 -- path/to/file
   ```
   This shows the differences for a specific file between two commits.

2. **Ignoring Whitespace**:
   ```sh
   git diff -w
   ```
   This ignores changes in whitespace, making it easier to see changes in content.

3. **Output Format Options**:
   ```sh
   git diff --stat
   ```
   This gives a summary of changes (file names and the number of insertions and deletions).

   ```sh
   git diff --name-only
   ```
   This lists the names of changed files only.

   ```sh
   git diff --name-status
   ```
   This shows the names and status of changed files (e.g., added, modified, deleted).

### Example Workflow

1. **Check for Unstaged Changes**:
   ```sh
   git diff
   ```

2. **Stage Some Changes**:
   ```sh
   git add file1.txt
   ```

3. **Check for Staged Changes**:
   ```sh
   git diff --staged
   ```

4. **Make More Changes and Commit**:
   ```sh
   git add file2.txt
   git commit -m "Updated file1 and file2"
   ```

5. **Compare with a Previous Commit**:
   ```sh
   git diff HEAD~1
   ```

6. **Compare with a Branch**:
   ```sh
   git diff feature-branch
   ```

7. **Compare with a Remote Branch**:
   ```sh
   git fetch origin
   git diff origin/main
   ```

### Practical Scenarios

- **Before Committing**:
  Use `git diff` to review changes before staging and committing them to ensure everything is correct.

- **Code Review**:
  When reviewing code, use `git diff commit1 commit2` to see what changes were made between two commits.

- **Merge Conflicts**:
  During a merge, use `git diff` to understand what changes are causing conflicts and how to resolve them.

- **Refactoring**:
  After refactoring code, use `git diff` to ensure that the changes are purely structural and don't alter functionality.

Understanding the `git diff` command and its various options can greatly enhance your ability to manage and review changes in your Git repository, making your version control workflow more efficient and precise.