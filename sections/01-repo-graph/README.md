# Git Repo as Graph

A git repository can be thought of in terms of a Directed Acyclic Graph (DAG), where commits are nodes. In Python pseudocode, we can write base git objects as:

```python
class Commit:
    hash: str
    snapshot: .zip
    parents: list[Commit]
    metadata: Metadata

class Metadata:
    author: str
    date: str
    message: str
    tags: list[str]

class Branch:
    name: str
    commit: Commit
```

With the following objects:

```python
A,...,F: Commit
main,dev,bugfix: Branch
```

We draw an example representation of a repository:

```yaml
A<--B<--C<--D <- dev
    ^    \
   main   E<--F <- bugfix
```

Key takes:
- Branches==Pointers: Branches are just cheap, simple pointers, easy to create and delete at will.
- One usually keeps track of branches only, not commits, so if we delete a branch, we lose track of nodes not accessible from other branches.
    * Delete "bugfix" above and we lose access to E and F.

## HEAD

```python
HEAD: Branch | Commit
```

HEAD is a special branch to symbolize the current state. It always points to the current commit or branch pointer:

- You are working on a branch == HEAD points to the branch == attached HEAD state
- You are on a commit directly (no branch) == HEAD points to the commit == detached HEAD state

### Attached

```
A<--B<--C<--D <- dev<-HEAD
    ^    \
   main   E<--F <- bugfix
```

- HEAD is attached to the dev branch == you're currently working on dev

### Detached

```
           HEAD
            v
A<--B<--C<--D <- dev
    ^    \
   main   E<--F <- bugfix
```

- HEAD points to commit D == you're on D but not on any branch

