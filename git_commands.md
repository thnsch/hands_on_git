# git commands

## staging to "index"
### stage files

	git add filename

### diff between staged and working
	
	git diff filename


## commit
### commit staged files

	git commit -m "Initial Commit"

### stage changes and deletions (no new files), then commit staged files

	git commit -a -m "Initial Commit"     

### show commit log

	git log      # chronological descend

## git stash
```
# Save tracked changes and clean the working tree
git stash

# Save changes with a message
git stash push -m "message"

# Also include untracked files
git stash push -u

# List saved stashes
git stash list

# Inspect latest stash
git stash show -p

# Reapply latest stash and keep it saved
git stash apply

# Reapply a specific stash and keep it saved
git stash apply stash@{n}

# Reapply latest stash and remove it from the list
git stash pop

# Remove a specific stash
git stash drop stash@{n}
```

## backtrack commands
### git restore
Default: copy index to working tree
```
# Index → working tree
git restore <path>

# HEAD → index
git restore --staged <path>

# HEAD → index and working tree
git restore --staged --worktree <path>

# Commit → working tree
git restore --source=<commit> <path>

# Commit → index and working tree
git restore --source=<commit> --staged --worktree <path>
```
	
### git reset
Default: copy HEAD to index
```
# Copy HEAD → index; working tree unchanged
git reset

# Copy HEAD → index for selected path (unstage); working tree unchanged
git reset <path>

# Move HEAD → commit; index and working tree unchanged
git reset --soft <commit>

# Move HEAD → commit and reset index; working tree unchanged
git reset <commit>

# Move HEAD → commit and reset index and working tree
git reset --hard <commit>

# Copy commit → index for selected path; working tree unchanged
git reset <commit> -- <path>      # '--': end-of-options marker
```
