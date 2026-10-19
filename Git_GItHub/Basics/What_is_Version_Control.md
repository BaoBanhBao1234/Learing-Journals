1. What Is Version Control?
- ==Version control, also called source control, is the practice of recording and managing changes to files over time.==
- ==A version control system (VCS) stores a project’s change history so you can inspect earlier versions, compare changes, and restore a previous state when needed.==
- Although it is commonly used for source code, version control can also track documentation, configuration, and other text-based project files.
- Git is a popular distributed version control system, but version control is the broader concept.

2. Why Version Control Matters
- ==It provides a reliable history of what changed, when it changed, who made the change, and the stated reason for it.==
- ==If a change introduces a bug, the history helps identify and undo or correct it.==
- ==It reduces the need to keep manual copies such as `project-final`, `project-final-2`, or `project-latest`.==
- ==It helps teams work on the same project while keeping each contribution reviewable and traceable.==
- ==It supports testing and release work by showing which changes belong to a particular version of a project.==

3. How Version Control Records Changes
- ==A project is stored in a repository, which contains project files and their recorded history.==
- ==A change is saved as a revision or commit. In Git, a commit records a snapshot of the project at that point, along with metadata such as its author, time, and message.==
- A diff shows the differences between two versions, helping people review exactly what was added, removed, or modified.
- Each saved change becomes part of a history that can be inspected later.

```text
Initial version
      |
Add a login page
      |
Fix a validation bug
      |
Current version
```

4. A Simple Version Control Workflow
- Make a small, focused change to the project.
- Review the change to check what will be recorded.
- Save it as a named revision or commit with a clear message.
- Continue working, compare revisions, or restore an earlier state when needed.
- In a team, share changes and integrate them with the project’s main line of work.

```bash
git status
git diff
git add login.py
git commit -m "Add login validation"
git log --oneline
```

- These are Git commands illustrating a common workflow; other version control systems may use different commands and terminology.

5. Working on Changes in Parallel
- ==A branch is an independent line of work. It lets a contributor develop a feature or fix without immediately changing the main line.==
- ==When the work is ready, it can be merged into another branch.==
- ==A conflict occurs when changes cannot be combined automatically, for example when two contributors edit the same lines in incompatible ways.==
- Contributors review and resolve conflicts, then test the combined result.
- ==Version control helps surface overlapping work and provides a way to integrate it without forcing contributors to take turns editing every file.==

6. Centralized and Distributed Version Control
- ==In a centralized VCS, a central server stores the main repository history, and contributors work with it over the network.==
- ==In a distributed VCS, each clone has its own repository and can contain the project’s history. Contributors can record and inspect many changes locally, then exchange work with other repositories==.
- Git is distributed. Teams can still use a shared remote repository as the collaboration point, but local work does not depend on contacting that server for every operation.

7. Version Control and Manual Backups
- ==A VCS is designed to record intentional project changes and support collaboration, comparison, and recovery.==
- It does not replace a separate backup plan: a repository can still be lost, damaged, or made inaccessible, so important work should also be backed up appropriately.
- Clear commit messages and focused changes make the history more useful to future readers.

8. Key Takeaways
- Version control records a project’s changes so earlier states can be inspected and recovered.
- Its history helps explain how and why the project changed.
- Branches and merges support parallel work; conflicts are reviewed and resolved when changes overlap.
- Git is one VCS, specifically a distributed one.

9. Sources
- [Inter-git: Introduction](https://inter-git.com/lessons/introduction)
- [Atlassian: What is version control?](https://www.atlassian.com/git/tutorials/what-is-version-control)
- [YouTube video](https://www.youtube.com/watch?v=2ReR1YJrNOM)
