1. Create & `cd` to a directory for your repo and its worktrees
```bash
mkdir worktrees-fun && cd worktrees-fun
```

Clone this repo into a hidden .bare folder
```bash
git clone --bare git@github.com:jonathan-harford-atg/worktrees-fun.git .bare
```

Tell the root folder where the Git history is hidden
```bash
echo "gitdir: ./.bare" > .git
```

3. Fix the fetch configuration to see all remote branches
```bash
git config remote.origin.fetch "+refs/heads/*:refs/remotes/origin/*"
```

4. Add a worktree (the main branch)
```bash
git worktree add main 
```

5. Add a worktree (creates branch if it doesn't already exist)
```bash
git worktree add my-worktree-branch
```

# Each folder correspond to a branch, everything is centralized
# Read the doc... or follow the article
