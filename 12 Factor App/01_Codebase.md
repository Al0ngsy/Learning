# 1. Codebase

Use **Git** to track your codebase, and have a **single codebase per app/service**.

- Multiple deploys from the same codebase are allowed (e.g., staging and production), but there should be a one-to-one relationship between codebase and app/service.
- Each codebase should be tracked in a revision control system, such as Git, Mercurial, or Subversion.
- Central repositories that support storing codebases: Github, Gitlab, Bitbucket, and Azure Repos.

Example Git commands:
```bash
# Initialize a new Git repository
git init

# Add files to the staging area
git add .

# Commit changes with a message
git commit -m "Initial commit"

# Push to a remote repository
git remote add origin <repository_url>
git push -u origin master
```

Or using Git GUI tools like GitHub Desktop, GitKraken, SourceTree or Git Graph Extension on VS Code can also help to manage the codebase visually.

## Key points

- Keep the codebase small and focused: one codebase per service.
- Use branching and CI practices to manage changes safely across environments.
