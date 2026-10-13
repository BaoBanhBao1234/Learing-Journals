1. Why Use Version Control?
- Version control keeps an organized history of changes to a project’s files.
- It helps individuals and teams understand how work has changed, recover from mistakes, and coordinate contributions.
- It is useful for source code as well as shared documents and other files that need a reliable change history.

2. Recover from Mistakes
- A change history lets you compare the current work with earlier versions and identify when an issue was introduced.
- If an edit breaks something, you can restore or reapply a known working version instead of rebuilding the work from memory.
- This makes experimentation safer because changes are recorded and can be reviewed or undone.

3. Know What Changed and Why
- A version control system can record who made a change and when it was saved.
- Descriptive commit messages explain the purpose of a change, making the history easier to understand later.
- This traceability helps with debugging, code review, audits, and onboarding contributors to an existing project.

4. Collaborate Without Losing Work
- Multiple contributors can work on separate changes at the same time.
- Branches keep features, fixes, or experiments isolated while they are developed and tested.
- Changes can be reviewed and merged into the shared project when they are ready.
- If edits overlap, the team can identify and resolve conflicts rather than silently overwriting someone else’s work.

5. Experiment and Review Safely
- A branch provides a place to test an idea without immediately changing the stable version of a project.
- Teams can run tests and review a change before merging it.
- Review gates and permissions can help control which changes reach a protected main branch.
- This encourages small, reversible experiments and can catch problems earlier.

6. Keep Teams Aligned on Current Files
- Version history helps contributors identify the latest approved changes and avoid relying on stale copies.
- For shared documents, keeping earlier versions and an audit trail can reduce confusion about who edited a file and when.
- Consistent review and approval practices make it clearer which version is ready to use or publish.

7. Support Releases and Ongoing Maintenance
- A recorded history helps teams understand which changes were included in a release.
- Teams can compare releases, investigate regressions, and apply fixes to older supported versions.
- The history also preserves useful project knowledge when contributors change or new people join.

8. Without Version Control
- People often create duplicate files with names such as `final`, `final-2`, or `latest`, making it hard to know which copy is authoritative.
- Changes can be overwritten, forgotten, or difficult to attribute.
- Parallel work may be combined late, increasing the chance of incompatible changes and rework.
- Recovering a previous working state may require manual reconstruction.

9. Example: A Team Feature Change
- A developer creates a branch for a new feature and commits focused changes with clear messages.
- The team reviews the branch and runs tests.
- After feedback and any needed fixes, the branch is merged into the main project.
- If a problem appears later, the team can inspect the change history to investigate and correct it.

```text
Create branch -> Make and record changes -> Review and test -> Merge -> Release
```

10. Key Takeaways
- Version control improves recovery, traceability, collaboration, and review.
- It makes experimentation safer by keeping work isolated and changes recorded.
- A clear history helps teams maintain software and shared documents over time.
- Version control supports backups and recovery, but a repository should still be included in an appropriate backup plan.

11. Sources
- [Inter-git: Introduction](https://inter-git.com/lessons/introduction)
- [TechRepublic: Benefits of Version Control](https://www.techrepublic.com/article/version-control-benefits/)
- [DocuWare: The Ultimate Guide to Document Version Control](https://start.docuware.com/blog/document-management/what-is-version-control-why-is-it-important)
