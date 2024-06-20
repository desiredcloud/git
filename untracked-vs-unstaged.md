## Untracked vs Unstaged

In Git, "untracked" and "unstaged" are terms that refer to the state of files in your working directory. Understanding the difference between these two terms is crucial for effectively managing changes in your Git repository.

### Untracked Files

**Untracked files** are files that are present in your working directory but are not being tracked by Git. This means that Git is not aware of these files and they are not part of the repository's version history. 

- **How they appear**: Untracked files typically show up when you use `git status`. They are listed under the "Untracked files" section.
- **Behavior**: Since they are not tracked, any changes to these files are not included in commits until you explicitly tell Git to track them.
- **How to track them**: You can add untracked files to the staging area using the `git add` command. For example:
  ```sh
  git add filename
  ```

### Unstaged Changes

**Unstaged changes** are modifications made to files that Git is already tracking, but these changes have not yet been added to the staging area. The staging area is a preparatory area where changes are reviewed before being committed to the repository.

- **How they appear**: Unstaged changes also show up when you use `git status`. They are listed under the "Changes not staged for commit" section.
- **Behavior**: These changes are in tracked files, but they are not yet part of the next commit. You need to stage them to include them in the next commit.
- **How to stage them**: You can add unstaged changes to the staging area using the `git add` command. For example:
  ```sh
  git add filename
  ```

### Example Scenario

Let's walk through an example to illustrate the difference:

1. **Create a New File (Untracked)**:
   ```sh
   echo "Hello, world!" > hello.txt
   ```
   When you run `git status`, you'll see:
   ```
   Untracked files:
     (use "git add <file>..." to include in what will be committed)
         hello.txt
   ```

2. **Stage the Untracked File**:
   ```sh
   git add hello.txt
   ```
   Now, if you run `git status`, `hello.txt` will appear in the "Changes to be committed" section, indicating it is staged.

3. **Modify a Tracked File (Unstaged)**:
   ```sh
   echo "Another line" >> hello.txt
   ```
   When you run `git status`, you'll see:
   ```
   Changes not staged for commit:
     (use "git add <file>..." to update what will be committed)
         modified:   hello.txt
   ```

4. **Stage the Unstaged Changes**:
   ```sh
   git add hello.txt
   ```
   After running `git add`, if you check `git status`, the changes will now be in the "Changes to be committed" section.

### Summary

- **Untracked Files**: Files that are not being tracked by Git. These files are new to the repository and have not been added to the staging area.
- **Unstaged Changes**: Modifications made to files that are already being tracked by Git but have not yet been added to the staging area.

In both cases, the `git add` command is used to move changes to the staging area, preparing them for the next commit. Understanding these concepts helps you manage your workflow and ensure that the right changes are included in your commits.