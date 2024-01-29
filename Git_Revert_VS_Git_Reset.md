# Title: Explanation of Git Revert Command

## Introduction:
The `git revert` command in Git is used to undo a previous commit while preserving the commit history. It's a powerful tool to revert changes without altering the commit lineage.

### Explanation:

#### Initial Commit History:
#### STEP-1)

"git log --oneline"

A --- B --- C --- D

In this diagram, the commit history consists of four commits: A, B, C, and D.

#### Git Revert
#### STEP-2)

"git revert <commit_id_of_commit"C">"

Using `git revert` to Revert Commit C:

To revert a specific commit (e.g., commit C), the `git revert` command is utilized. It creates a new commit that undoes the changes introduced by commit C:


A --- B --- C --- D
            |
          Revert C

#### STEP 3)

"git log --oneline"

The "Revert(C)" commit is a new commit that negates the changes made in commit C, effectively undoing those changes. The commit history now looks like this:


A --- B --- C --- D --- Revert(C)

The "Revert(C)" commit undoes the changes from commit C without altering the commit history.

======================================================================
======================================================================

### Advantages of `git revert`:
- It's a safe way to undo changes without altering commit history.
- Useful for collaborative development environments.

### Conclusion:
The `git revert` command is a valuable tool to safely undo changes in a Git repository, allowing for precise control over modifications while maintaining a comprehensive commit history.

###==================================================###

# Title: Explanation of GIT RESET 

## Manipulating Git History with git reset:

Here's a more detailed explanation of your scenario using diagrams, focusing on the different git reset options and their effects:

### Scenario:

    You have a linear commit history: A -> B -> C -> D.
    Mistake: You accidentally committed sensitive information like keys in commit C.
    Goal:
        Get back to state B: Discard commits C and D.
        Prepare for manipulation: Cleanly work on subsequent commits after B.

Solution: Use git reset with different flags to achieve the desired outcome:

#### STEP 1)

### 1. git reset --hard <COMMIT "B" ID>:

    Diagram:

Before:      A--B--C--D

After:       A--B
               /
              C--D (lost)

    Explanation: This is a hard reset. It moves both the HEAD and the working directory index to the specified commit (B).
    Effects:
        Commits C and D are permanently discarded from the history, along with their changes.
        Any unstaged changes in your workspace are also lost.
        Use this cautiously as it's irreversible!

#### STEP 2)

2. git reset --soft <COMMIT "B" ID>:

    Diagram:

Before:      A--B--C--D

After:       A--B (staged C--D)

    Explanation: This is a soft reset. It moves the HEAD back to the specified commit (B), but keeps the changes from commits C and D staged.
    Effects:
        Commits C and D remain in the history, but are unlinked from the current branch.
        Their changes are kept staged in your working directory, allowing you to review and potentially include them in new commits.
        Use this if you want to review/modify changes before discarding them.

#### OR
#### STEP 

3. git reset --mixed <COMMIT "B" ID>:

    Diagram:

Before:      A--B--C--D

After:       A--B--C (unmodified, unstaged)
                 /
                D (lost)

    Explanation: This is a mixed reset. It moves the HEAD back to the specified commit (B), but keeps the changes from commits C and D in your working directory, but unstaged.
    Effects:
        Commits C and D remain in the history, but unlinked from the current branch.
        Their changes are kept unstaged in your workspace, requiring explicit staging before being included in new commits.
        Use this if you want to discard specific changes from C or D while keeping others.

Remember:

    Always double-check the commit ID before using git reset.
    Consider using git stash to temporarily shelve unwanted changes before resetting.
    Be cautious with hard resets as they are irreversible.

Additional options:

    You can also specify a range of commits using git reset HEAD~2 to move back multiple commits.
    Consider using git rebase for more advanced history manipulation, but it requires careful handling and should be used with caution.

I hope this explanation and diagrams clarify the different ways to use git reset to manipulate your Git history effectively in your scenario. Don't hesitate to ask if you have further questions!