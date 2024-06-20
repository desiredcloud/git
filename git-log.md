## Git log

The `git log` command is one of the most powerful and frequently used commands in Git. It allows you to view the commit history of your repository, showing information about each commit. Here’s a comprehensive guide on how to use `git log` and its various options.

### Basic Usage

1. **Simple Commit History**:
   ```sh
   git log
   ```
   This shows a list of commits in reverse chronological order (most recent commits first), including the commit hash, author, date, and commit message.

### Common Options

1. **Limit the Number of Commits**:
   ```sh
   git log -n <number>
   ```
   Shows only the last `<number>` of commits. For example, `git log -n 3` displays the three most recent commits.

2. **Pretty Print**:
   ```sh
   git log --pretty=<format>
   ```
   Formats the log output. Common formats include:
   - `oneline`: Each commit on a single line.
   - `short`: Short format (commit hash and commit message).
   - `medium`: Medium format (default, shows hash, author, date, and message).
   - `full`: Full format (includes committer information).
   - `fuller`: Like `full` but with more date details.

   Example:
   ```sh
   git log --pretty=oneline
   ```

3. **Graphical Representation**:
   ```sh
   git log --graph
   ```
   Adds a graphical representation of the commit history, showing branches and merges.

4. **Show Changes**:
   ```sh
   git log -p
   ```
   Displays the patch (diff) introduced in each commit. This shows the changes made in each commit.

5. **Statistical Summary**:
   ```sh
   git log --stat
   ```
   Shows a summary of changes for each commit, including the number of insertions and deletions per file.

6. **Filter by Author**:
   ```sh
   git log --author="Author Name"
   ```
   Shows commits by a specific author.

7. **Filter by Date**:
   ```sh
   git log --since=<date> --until=<date>
   ```
   Filters commits by date. Dates can be specified in various formats like `2023-01-01`, `yesterday`, `2 weeks ago`, etc.

   Example:
   ```sh
   git log --since="2 weeks ago"
   ```

8. **Filter by File**:
   ```sh
   git log -- <file>
   ```
   Shows commits that include changes to a specific file.

   Example:
   ```sh
   git log -- README.md
   ```

9. **Decorate**:
   ```sh
   git log --decorate
   ```
   Shows references (like branches and tags) next to commit messages.

### Combining Options

1. **Graphical and Pretty Print**:
   ```sh
   git log --graph --pretty=oneline
   ```
   Combines graphical representation with a single-line format.

2. **Filter by Author and Date**:
   ```sh
   git log --author="Author Name" --since="2023-01-01"
   ```

3. **Show Changes for a Specific File**:
   ```sh
   git log -p -- <file>
   ```

### Advanced Options

1. **Show Commit History in Reverse Order**:
   ```sh
   git log --reverse
   ```

2. **Find Commits that Introduced a Bug**:
   ```sh
   git log -S "buggy code snippet"
   ```
   Searches for commits that introduced or removed the specified code snippet.

3. **Abbreviated Commit Hashes**:
   ```sh
   git log --abbrev-commit
   ```
   Shows abbreviated commit hashes instead of full hashes.

4. **Merges Only**:
   ```sh
   git log --merges
   ```
   Shows only merge commits.

### Example Scenarios

1. **Basic Log**:
   ```sh
   git log
   ```

2. **Last 5 Commits**:
   ```sh
   git log -n 5
   ```

3. **Pretty Print with Graph**:
   ```sh
   git log --graph --pretty=oneline --abbrev-commit
   ```

4. **Commits by a Specific Author in the Last Month**:
   ```sh
   git log --author="Jane Doe" --since="1 month ago"
   ```

5. **Changes to a Specific File**:
   ```sh
   git log -p -- README.md
   ```

6. **Commits with Detailed Stats**:
   ```sh
   git log --stat --decorate
   ```

### Understanding Output

Here’s an example of what the basic `git log` output looks like:

```
commit 1a2b3c4d5e6f7g8h9i0jklmnopqrstuvwxyza (HEAD -> main, origin/main, origin/HEAD)
Author: John Doe <john@example.com>
Date:   Mon Feb 1 12:34:56 2023 +0000

    Initial commit
```

- **commit**: The unique hash identifier of the commit.
- **Author**: The name and email of the person who made the commit.
- **Date**: The date and time when the commit was made.
- **Message**: The commit message describing the changes.

Using the `git log` command effectively allows you to track the history of your project, understand changes, and gain insights into the development process. It is a vital tool for any developer working with Git.

---

## Git shortlog


The `git shortlog` command is a useful Git tool for summarizing the commit history. It groups commits by author and provides a brief summary of each commit message, making it easier to see the contributions of each developer in a project.

### Basic Usage

1. **Simple Shortlog**:
   ```sh
   git shortlog
   ```
   This command provides a summary of commits grouped by author, with each commit message listed under the corresponding author.

### Common Options

1. **Summarize by Number of Commits**:
   ```sh
   git shortlog -s
   ```
   This shows a summary with the number of commits per author, without listing the commit messages.

   Example:
   ```
   15  Alice
   10  Bob
    5  Carol
   ```

2. **Summarize by Author and Number of Commits**:
   ```sh
   git shortlog -s -n
   ```
   This lists authors sorted by the number of commits in descending order.

   Example:
   ```
   15  Alice
   10  Bob
    5  Carol
   ```

3. **Summarize by Commit Messages**:
   ```sh
   git shortlog -n
   ```
   This sorts authors by the number of commits but includes commit messages.

   Example:
   ```
   Alice (15):
       Commit message 1
       Commit message 2
       ...
       
   Bob (10):
       Commit message 1
       Commit message 2
       ...
   ```

4. **Group by Email**:
   ```sh
   git shortlog -e
   ```
   This groups commits by author email addresses.

   Example:
   ```
   Alice <alice@example.com> (15):
       Commit message 1
       Commit message 2
       ...
   ```

5. **Filter by Commits Since a Specific Date**:
   ```sh
   git shortlog --since="2023-01-01"
   ```
   This shows commits made since the specified date, grouped by author.

6. **Filter by Commits Until a Specific Date**:
   ```sh
   git shortlog --until="2023-01-01"
   ```
   This shows commits made up until the specified date, grouped by author.

7. **Range of Commits**:
   ```sh
   git shortlog commit1..commit2
   ```
   This summarizes commits within a specific range of commits.

### Example Scenarios

1. **Basic Summary**:
   ```sh
   git shortlog
   ```
   This shows all commits grouped by author with commit messages.

2. **Summary with Commit Counts**:
   ```sh
   git shortlog -s
   ```
   This displays a summary with the number of commits per author.

3. **Sorted Summary by Number of Commits**:
   ```sh
   git shortlog -s -n
   ```
   This lists authors sorted by the number of commits in descending order.

4. **Grouped by Email**:
   ```sh
   git shortlog -e
   ```
   This groups commits by author email addresses.

5. **Filter by Date**:
   ```sh
   git shortlog --since="2023-01-01" --until="2023-12-31"
   ```
   This shows commits within the specified date range, grouped by author.

6. **Range of Commits**:
   ```sh
   git shortlog 1a2b3c..4d5e6f
   ```
   This summarizes commits within the specified commit range.

### Practical Scenario

Suppose you want to prepare a summary report of contributions for the last month:

1. **Summary Report for the Last Month**:
   ```sh
   git shortlog --since="1 month ago" -s -n
   ```

   This provides a summary of the number of commits made by each author in the last month, sorted by the number of commits.

### Output Example

Here’s what the `git shortlog` output might look like:

```
Alice (15):
    Initial commit
    Added feature X
    Fixed bug in feature X
    ...

Bob (10):
    Added documentation
    Refactored codebase
    Updated dependencies
    ...

Carol (5):
    Implemented feature Y
    Fixed typo
    ...
```

- **Alice (15)**: Shows that Alice has made 15 commits, followed by a brief summary of each commit message.
- **Bob (10)**: Indicates Bob’s 10 commits with their respective messages.
- **Carol (5)**: Lists Carol’s 5 commits and their summaries.

### Summary

The `git shortlog` command is a powerful way to get an overview of contributions in a Git repository, summarizing commit activity by author and providing insight into the distribution of work among team members. This can be particularly useful for project management, reporting, and recognizing contributions in collaborative projects.