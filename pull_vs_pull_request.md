# Pull vs Pull Request vs Push

## Git Pull
**What it is:** A Git command that downloads and merges changes from a remote repository to your local repository.

**When to use:** When you want to get the latest changes from others working on the same repository.

**Example:**
```bash
git pull origin main
```

## Pull Request (PR)
**What it is:** A GitHub feature that proposes changes to be merged into a repository. It's a request for others to review and pull your changes.

**When to use:** When you want to contribute changes to a repository (especially open source projects or team projects where you don't have direct push access).

**Example:** Creating a PR on GitHub after pushing a feature branch.

## Git Push
**What it is:** A Git command that uploads your local commits to a remote repository.

**When to use:** When you want to share your local changes with others or backup your work to a remote server.

**Example:**
```bash
git push origin feature-branch
```

## Key Differences

### Direction of Data Flow
- **Pull:** Remote → Local (download changes)
- **Push:** Local → Remote (upload changes)
- **Pull Request:** Proposal to merge (no direct data flow, creates discussion)

### Permissions Required
- **Pull:** Read access to repository
- **Push:** Write access to repository
- **Pull Request:** Can be created by anyone (even without write access if repository allows forks)

### Use Cases
- **Pull:** Staying up-to-date with team changes
- **Push:** Sharing your work, deploying changes
- **Pull Request:** Code review, contributing to projects

### Conflict Handling
- **Pull:** Can cause merge conflicts locally
- **Push:** Can be rejected if remote has new commits
- **Pull Request:** Conflicts are identified during review, resolved before merge

## Real-world Analogy
- **Pull:** Like downloading the latest version of an app
- **Push:** Like uploading your photos to cloud storage
- **Pull Request:** Like submitting a job application - you're proposing yourself for consideration

## Sources
- GitHub Docs: https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository
- Atlassian Git Tutorial: https://www.atlassian.com/git/tutorials/syncing