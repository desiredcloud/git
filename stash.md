## Git stash

The `git stash` command in Git is a useful tool for temporarily saving changes you've made to your working directory so that you can switch branches or perform other tasks without committing those changes. It allows you to "stash" your modifications and come back to them later. Here’s a detailed guide on how to use `git stash` effectively:

### Basic Usage

1. **Stashing Changes**:
   ```sh
   git stash
   ```
   This command saves your local modifications (both staged and unstaged changes) and reverts your working directory to match the HEAD commit. Your changes are now stored in the stash list.

2. **Stashing with a Message**:
   ```sh
   git stash save "Your message"
   ```
   This allows you to add a description to your stash, making it easier to remember what changes were saved.

### Viewing Stashes

1. **List Stashes**:
   ```sh
   git stash list
   ```
   This command displays a list of all stashes you've created, showing the stash name, commit it was based on, and any message you provided.

### Applying Stashes

1. **Applying the Latest Stash**:
   ```sh
   git stash apply
   ```
   This command applies the most recent stash to your working directory without removing it from the stash list.

2. **Applying a Specific Stash**:
   ```sh
   git stash apply stash@{n}
   ```
   Replace `n` with the stash index you want to apply. You can find the index using `git stash list`.

3. **Applying and Removing the Latest Stash**:
   ```sh
   git stash pop
   ```
   This applies the most recent stash and then removes it from the stash list.

4. **Applying and Removing a Specific Stash**:
   ```sh
   git stash pop stash@{n}
   ```
   Applies and removes the specified stash.

### Dropping Stashes

1. **Dropping the Latest Stash**:
   ```sh
   git stash drop
   ```
   This removes the most recent stash from the stash list without applying it.

2. **Dropping a Specific Stash**:
   ```sh
   git stash drop stash@{n}
   ```
   Removes the specified stash from the stash list.

3. **Clearing All Stashes**:
   ```sh
   git stash clear
   ```
   This command removes all stashes from the stash list.

### Creating and Applying Stashes with Additional Options

1. **Stashing Untracked Files**:
   ```sh
   git stash -u
   ```
   This includes untracked files in the stash. This is useful if you have new files that are not yet tracked by Git.

2. **Stashing Only Unstaged Changes**:
   ```sh
   git stash --keep-index
   ```
   This stashes only the changes that are not staged, leaving the staged changes intact.

3. **Including Ignored Files**:
   ```sh
   git stash -a
   ```
   This includes ignored files in the stash.

4. **Applying Stash with Conflicts**:
   When applying a stash, you might encounter conflicts. Resolve them as you would with any other merge conflict, and then mark them as resolved.

### Example Workflow

1. **Start Working on a Feature**:
   You start making changes to several files.

2. **Need to Switch Branches**:
   You realize you need to switch to another branch to fix a critical bug, but you don't want to commit your current work.

3. **Stash Your Changes**:
   ```sh
   git stash save "WIP: working on feature X"
   ```

4. **Switch Branches**:
   ```sh
   git checkout bugfix-branch
   ```

5. **Fix the Bug and Commit**:
   You make the necessary changes, commit them, and possibly push them to the remote repository.

6. **Switch Back to Your Feature Branch**:
   ```sh
   git checkout feature-branch
   ```

7. **Apply Your Stashed Changes**:
   ```sh
   git stash pop
   ```

8. **Continue Working**:
   Your changes are reapplied, and you can continue working on your feature.

### Practical Scenarios

1. **Stashing and Switching Branches**:
   ```sh
   git stash
   git checkout another-branch
   # Do some work on another-branch
   git checkout feature-branch
   git stash pop
   ```

2. **Stashing Untracked Files**:
   ```sh
   git stash -u
   ```

3. **Viewing and Applying a Specific Stash**:
   ```sh
   git stash list
   git stash apply stash@{1}
   ```

4. **Clearing All Stashes**:
   ```sh
   git stash clear
   ```

### Summary

The `git stash` command is a powerful tool for managing your workflow in Git. It allows you to save your work temporarily and return to it later, making it easier to switch contexts without losing your progress. Whether you need to quickly switch branches, handle urgent bug fixes, or simply clean your working directory, `git stash` provides a flexible way to manage your changes.