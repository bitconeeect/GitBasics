# Git Repository Folder

## Working Directory

A typical project might look like this:

```
my-project/            <- Working Directory
├── .git/              <- Repository
├── src/
│   ├── main.py
│   └── utils.py
├── tests/
│   └── test_main.py
├── README.md
└── requirements.txt
```

Files in the working directory are either being tracked by Git or not.
Untracked files are files in your working directory that Git doesn't monitor, such as:
- New files you've created but haven't yet added to Git
- Files you've explicitly told Git to ignore

## Repository (.git directory)

Inside your working directory you will find the Git repository folder, where all versions of your files and the history of your project is stored. It's where the objects from section 1 live. It looks something like this:

```
.git/                   <- Repository
├── HEAD                <- Points to the current branch/commit
├── config              <- Repository configuration
├── hooks/              <- Scripts that run at certain events
├── index               <- The staging area
├── logs/               <- Records of reference updates
├── objects/            <- Database of all versions of files
│   ├── 8d/
│   │   └── 629a6ffc1e5e3a0346681bb7576bowc3e9a0f
│   └── ...
└── refs/               <- Pointers to commits (branches, tags)
    ├── heads/          <- All branches
    │   ├── main
    │   └── feature-x
    └── tags/           <- All tags
```

## Branches

A branch is simply a file in `.git/refs/heads/` that contains the commit hash it points to. For example:

```
# .git/refs/heads/main
8d629a6ffc1e5e3a0346681bb7576bowc3e9a0f
```

*Check it out now! Open the file.*

### The HEAD Pointer

`HEAD` is the special pointer that registers which branch you're currently on: 

```
# .git/HEAD
ref: refs/heads/main
```

This means you're on the `main` branch.

*Try it! Change to a different branch or checkout a commit and see the file changing.*

## Staging Area (Index)

The `index` file inside `.git` is where Git keeps track of what will go into your next commit. It contains all changes that you have already marked (*staged*) for inclusion in the next commit.

When you make changes to files in your working directory, you need to explicitly tell Git which changes you want to include in your next commit.

You can stage entire files, or all changes in an already tracked file, but you can also be selective and stage only some of the changes within a file. A changed segment within a file is called a *hunk*.

### Adding Segments to Staging in SourceTree

The "File Status" tab shows staged and unstaged changes with color coding:
- Double-click on a file to view its changes.
- The diff view appears, showing changes with added (green), removed (red), and modified (yellow) lines.
- Here you can stage segments of changes with "Stage hunk" or "Stage this line".

*Try it out! Make changes to different parts of the text and stage part of it.*

## Commits

When you commit:

1. Git takes the contents of the staging area
2. Creates a new commit object in the `.git/objects` directory
3. If we are at a branch, update the current branch pointer to the new commit
4. Clears the staging area

```
               HEAD
                v
               dev
                v
A<--B<--C<--D<--E
        ^
       main
```

When you create a new commit:

```
                   HEAD
                    v
                   dev
                    v
A<--B<--C<--D<--E<--F
        ^
       main
```

### Commit Best Practices

1. Make atomic commits (one logical change per commit)
2. Write clear commit messages:
   - First line: concise summary in imperative mood (50 chars or less)
   - Skip a line, then detailed explanation if needed
       * Explain *why* the change was made, not only *what* changed

Example:
```
Improve data loading speed with pandas

Pandas was much faster at loading the data than numpy,
with small memory usage increase.
```

