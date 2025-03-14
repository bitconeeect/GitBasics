# A model of Git

This repository serves as an interactive learning environment to understand Git's core concepts and operations. We focus on creating a useful representation of what is happening behind the scenes when you stage, commit, push, rebase, merge...

Git's power comes with complexity that can be intimidating. Many Git concepts are counterintuitive or confusingly named ("checkout? detached HEAD??"). This repository aims to:

1. Provide a pre-configured Git repository in an advanced state for experimentation
2. Clarify Git's core concepts through diagrams, pythonic objects, and hands-on exercises
3. Offer recovery techniques for common Git mistakes
4. Review common Git and SourceTree configs that can make things easier

This guide is designed for SourceTree. Each section includes:

- Explanations of Git concepts with diagrams
- SourceTree instructions for complex operations
- Hands-on exercises

## Learning Path

### Git Repository Graph
- **Commits**: Nodes in a directed acyclic graph
- **Branches**: Movable pointers to commits
- **HEAD**: The symbolic reference to the current point

### Git Repository Folder
- **Branching**: Creating and moving pointers
- **Staging Changes**: Understanding the index/staging area
- **Committing**: Creating new nodes in the commit graph

### Advanced Operations
- **Merging**: Combining work from different branches
- **Rebasing**: Rewriting history by changing parent commits
- **Cherry-picking**: Applying specific commits to different branches
- **Interactive Rebasing**: Squashing, editing, and reordering commits
- **Resolving Merge Conflicts**: Strategies and best practices

### Remote Operations
- **Remotes**: Server-side repository
- **Fetching/Pulling/Pushing**: Updating local and remote repos
- **Merge/Pull Requests**: Collaboration workflows
- **Tracking Branches**: How local and remote branches relate

### Recovery Techniques
- **Reflog**: Your safety net for recovering lost commits
- **Reset vs. Revert**: Different ways to undo changes
- **Stashing**: Temporarily storing uncommitted changes

### Git and SourceTree Configuration
- **Essential Git Configs**: User identity, line endings, default branch, etc.
- **SourceTree Customization**: UI preferences, custom actions, and keyboard shortcuts
- **Git Hooks**: Automating tasks with pre-commit and post-commit hooks
- **Aliases and Custom Commands**: Streamlining your workflow

### Real-world Branching Strategies
- **GitFlow**: Feature, release, and hotfix branches
- **Trunk-based Development**: Minimizing long-lived branches
- **GitHub Flow**: Simplified workflow centered around pull requests

