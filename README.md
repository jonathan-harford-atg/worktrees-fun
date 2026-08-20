Create & `cd` to a directory for your repo's worktrees
```bash
mkdir worktrees-fun && cd worktrees-fun
```

Clone _just_ the repo history to a `.bare` folder
```bash
git clone --bare git@github.com:jonathan-harford-atg/worktrees-fun.git .bare
```

Declare where the Git history is (so you can run git commands from here)
```bash
echo "gitdir: ./.bare" > .git
```

Fix the fetch configuration to see all remote branches, since bare clones don't automatically track remotes.
```bash
git config remote.origin.fetch "+refs/heads/*:refs/remotes/origin/*"
```

Now that you're tracking, fetch
```bash
git fetch --all
```

Create a worktree off an existing branch
```bash
git worktree add main 
```

Create a worktree and a corresponding branch (note it's the same command)
```bash
git worktree add my-wtree-branch
```

## End result:

```
worktrees-fun/
├── .bare/           # Git history
├── main             # Worktree 1
└── my-wtree-branch  # Worktree 2
```

## Friction

- VSCode can't be made to show repo name in title ([#251596](https://github.com/microsoft/vscode/issues/251596))

## References

- [Git worktree like a boss](https://dev.to/metal3d/git-worktree-like-a-boss-2j1b)