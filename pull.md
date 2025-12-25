# Pull

## Explanation
Pull is a Git command that fetches changes from a remote repository and merges them into your current branch. It's essentially a combination of two commands: `git fetch` (downloads changes) followed by `git merge` (integrates changes into your current branch). This keeps your local repository synchronized with the remote repository.

## Key Points
- Downloads latest changes from remote repository
- Automatically merges changes into your current branch
- Can cause merge conflicts if there are conflicting changes
- Updates your local repository with work done by others
- Safe to run multiple times (idempotent operation)

## Use Cases
- Getting latest changes from a team project
- Syncing with the main branch before starting work
- Updating your local repository after others have pushed changes
- Keeping forks synchronized with upstream repositories

## Command Examples
```bash
git pull origin main          # Pull from origin's main branch
git pull --rebase origin main # Pull with rebase instead of merge
git pull --no-ff origin main  # Pull without fast-forward
```

## Sources
- GitHub Docs: https://docs.github.com/en/get-started/using-git/getting-changes-from-a-remote-repository
- Git Documentation: https://git-scm.com/docs/git-pull