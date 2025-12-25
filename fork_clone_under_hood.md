# What Happens Under the Hood: Fork vs Clone

## Fork (GitHub Operation)

### What Happens on GitHub's Servers
1. **Repository Duplication:** GitHub creates a complete server-side copy of the repository
2. **New Repository Creation:** A new repository is created under your account with the same name (or custom name)
3. **Remote Tracking:** Your fork gets a reference to the original repository called "upstream"
4. **Branch Preservation:** All branches, tags, and commit history are copied
5. **Permissions:** You become the owner with full control over your fork

### Network Operations
- Happens entirely on GitHub's servers
- No data transfer to your local machine
- Creates a new repository URL under your account
- Original repository remains unchanged

### Behind the Scenes
```bash
# What GitHub does internally:
cp -r /original/repo /your-account/forked-repo
git remote add upstream /original/repo
```

## Clone (Git Operation)

### What Happens on Your Local Machine
1. **Repository Download:** Git downloads all commits, trees, and blobs from the remote
2. **Local Repository Creation:** Creates a `.git` directory with full repository history
3. **Working Directory Setup:** Checks out the default branch (usually main/master)
4. **Remote Configuration:** Sets up `origin` remote pointing to the cloned repository
5. **Branch Tracking:** Creates local branches that track remote branches

### Network Operations
- Downloads compressed repository data over HTTPS/SSH
- Transfer includes: commits, trees, blobs, refs, and configuration
- Can be resumed if interrupted (partial clones)
- Creates local copy of all repository data

### Behind the Scenes
```bash
# What git clone does:
mkdir repo-name
cd repo-name
git init
git remote add origin <url>
git fetch origin
git checkout -b main origin/main
```

## Key Differences in Implementation

### Data Location
- **Fork:** Data stays on GitHub servers, creates new repository
- **Clone:** Data is downloaded to your local machine

### Repository Relationship
- **Fork:** Creates independent repository with upstream link
- **Clone:** Creates local copy linked to remote repository

### Storage Impact
- **Fork:** Uses GitHub's storage quota for your account
- **Clone:** Uses your local disk space

### Network Usage
- **Fork:** Minimal network usage (just API calls)
- **Clone:** Downloads entire repository (can be large for big repos)

## Advanced Concepts

### Shallow Cloning
```bash
git clone --depth 1 <url>  # Only latest commit
```
- Downloads minimal history
- Faster for large repositories
- Limited git log access

### Partial Cloning
```bash
git clone --filter=blob:none <url>  # No blobs initially
```
- Downloads repository structure without large files
- Files downloaded on-demand
- Saves bandwidth and storage

## Sources
- GitHub Engineering Blog: https://github.blog/engineering/under-the-hood/
- Git Documentation: https://git-scm.com/docs/git-clone
- Pro Git Book: https://git-scm.com/book/en/v2/Git-Internals-Transfer-Protocols