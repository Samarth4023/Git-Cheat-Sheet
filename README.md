# **📝 Git Cheat Sheet: The Ultimate Guide**  
_Last Updated: 2025_

## **📌 Basic Configuration**
```sh
git config --global user.name "Your Name"                # Set user name
git config --global user.email "you@example.com"         # Set email
git config --global color.ui auto                        # Enable colored output
git config --global core.editor nano                     # Set default editor
git config --global core.autocrlf true                   # Auto handle line endings
git config --list                                        # List all configuration
```

---

## **📁 Repository Setup**
```sh
git init                        # Initialize a new repository
git clone <repo_url>            # Clone an existing repository
git remote add origin <url>     # Add remote repository
git remote add <name> <url>     # Add a new remote repository
git remote -v                   # View remote repositories
git remote remove <name>        # Remove remote repository
git remote show <name>          # Show information about a remote
```

---

## **📌 Basic Operations**
```sh
git status                      # Check repository status
git add <file>                  # Stage a specific file
git add .                       # Stage all files
git commit -m "Message"         # Commit changes
git commit -am "Message"        # Add & commit in one step
git log                         # View commit history
git log --oneline               # Compact log
git log --graph --decorate      # Log with branches visualization
```

---

## **🔄 Branching & Merging**
```sh
git branch                      # List branches
git branch <branch_name>        # Create new branch
git checkout <branch_name>      # Switch to branch
git checkout -b <branch_name>   # Create & switch branch
git merge <branch_name>         # Merge branch into current
git branch -d <branch_name>     # Delete branch
git branch -D <branch_name>     # Force delete branch
git branch --show-current       # Show current branch
```

---

## **⏪ Undo Changes**
```sh
git checkout -- <file>          # Discard changes in working directory
git restore <file>              # Alternative to checkout (Git v2.23+)
git reset HEAD <file>           # Unstage file (keep changes)
git reset --hard                # Reset all changes (CAUTION)
git revert <commit>             # Create a new commit that undoes a previous one
```

---

## **🚀 Pushing & Pulling**
```sh
git push origin <branch>        # Push to remote branch
git push <remote> <branch>      # Push changes to a remote repository
git push -u origin <branch>     # Push and track upstream
git push --force                # Force push (use with caution)
git pull origin <branch>        # Pull latest changes
git pull --rebase               # Pull and rebase instead of merging
git fetch                       # Fetch changes without merging
git fetch <remote>              # Fetch changes from a remote repository
git fetch --prune               # Fetch and remove deleted remote branches
```

---

## **🛠️ Low-Level Internal Commands (Plumbing)**
These are the deep internal commands that Git uses under the hood.
```sh
git apply                     # Apply a patch to files
git cat-file                  # Show object contents (blob, commit, tag, tree)
git check-ignore              # Show files ignored by .gitignore
git check-attr                # Show attributes of files
git cherry                    # Find commits that exist in one branch but not another
git commit-tree               # Create a commit object manually
git count-objects             # Count the number of objects in the database
git diff-index                # Compare index with another tree or commit
git for-each-ref              # Show all references in repository
git hash-object               # Compute SHA-1 hash of a file
git index-pack                # Build pack index file
git merge-base                # Find common ancestor of two commits
git mktag                     # Create a tag object manually
git mktree                    # Create a tree object manually
git pack-objects              # Create a packed object file
git prune                     # Remove unreachable objects
git read-tree                 # Read tree information into index
git rev-list                  # Show list of commits reachable from a reference
git rev-parse                 # Parse and convert revision names
git symbolic-ref              # Read, change, or delete symbolic refs
git unpack-objects            # Unpack objects from a pack file
git update-index              # Manage Git index manually
git verify-pack               # Validate packed Git objects
git write-tree                # Create a tree object from current index
```

---

## **🕵️‍♂️ Stashing**
```sh
git stash                       # Save current work temporarily
git stash list                  # Show stashed changes
git stash apply                 # Apply last stashed change
git stash pop                   # Apply and remove from stash
git stash drop                  # Delete last stash
git stash clear                 # Delete all stashes
```

---

## **🔄 Rebasing**
```sh
git rebase <branch>             # Rebase onto another branch
git rebase -i HEAD~3            # Interactive rebase last 3 commits
git rebase --abort              # Cancel rebase
git rebase --continue           # Continue after resolving conflicts
```

---

## **🔄 Reset vs. Revert**
```sh
git reset --mixed HEAD~1       # Undo commit (keep changes unstaged)
git reset --soft HEAD~1        # Undo last commit (keep changes staged)
git reset --hard HEAD~1        # Undo last commit (discard changes)
```

---

## **🔍 Searching & Comparing**
```sh
git grep "pattern"              # Search for text in repo
git diff                        # Show unstaged changes
git diff --staged               # Show staged changes
git diff <branch1>..<branch2>   # Compare two branches
git blame <file>                # Show who changed what line
```

---

## **🔄 Tagging**
```sh
git tag                                  # List all tags
git tag <tagname>                        # Create a new tag
git tag -a <tagname> -m "msg"            # Create annotated tag
git push origin <tagname>                # Push a tag
git push --tags                          # Push all tags
git tag -d <tagname>                     # Delete local tag
git push origin --delete <tagname>       # Delete remote tag
```

---

## **💣 Deleting & Cleaning**
```sh
git rm <file>                   # Remove file from repo & working dir
git rm --cached <file>          # Remove from repo but keep locally
git mv                          # Move or rename a file
git clean -f                    # Remove untracked files
git clean -fd                   # Remove untracked files & directories
```

---

## **⏳ Working with Commits**
```sh
git commit --amend -m "New message"  # Change last commit message
git cherry-pick <commit_hash>        # Apply specific commit from another branch
git reflog                           # Show history of HEAD changes
```

---

## **👥 Collaborating**
```sh
git pull --rebase origin main        # Pull with rebase
git push origin <branch> --force     # Force push (use cautiously)
git merge --no-ff <branch>           # Merge without fast-forward
git merge --squash <branch>          # Merge but keep commits as one
```

---

## **🔐 Managing Credentials**
```sh
git credential-cache exit                      # Clear cached credentials
git credential reject https://github.com
git credential approve https://github.com
```

---

## **🌎 Working with Submodules**
```sh
git submodule add <repo_url>                    # Add submodule
git submodule update --init --recursive         # Clone/update submodules
git submodule foreach git pull origin main      # Update all submodules
git submodule deinit -f --all                   # Remove all submodules
```

---

## **🧪 Advanced Git Features**
```sh
git show <commit>              # Show details of a specific commit
git shortlog                   # Summarize commit history by author
git whatchanged                # Show file changes with commit history
git archive                    # Create an archive from a repository
git describe                   # Describe commits in a readable format
git log --graph --oneline      # Show commits in a compact graph
git bisect start               # Start binary search for bugs
git bisect bad                 # Mark current commit as bad
git bisect good <commit>       # Mark commit as good
git bisect reset               # End bisect session
```

---

## **📦 Working with Large Files**
```sh
git lfs install                                             # Install Git LFS
git lfs track "*.zip"                                       # Track large files
git add .gitattributes                                      # Add LFS config
git lfs migrate import --everything --include="*.zip"       # Migrate existing files
```

---

## **🛠️ Git Maintenance & Cleanup**
```sh
git fsck                      # Check repository integrity
git gc                        # Cleanup unnecessary files
git prune                     # Remove unreachable objects
git repack                    # Pack objects to optimize space
git verify-commit <commit>    # Check commit validity
git verify-tag <tag>          # Check tag validity
```

---

## **🐳 Working with Aliases**
```sh
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.st status
git config --global alias.unstage "reset HEAD --"
git config --global alias.last "log -1 HEAD"
```

---

## **📊 Viewing Statistics**
```sh
git shortlog -sn                       # Show commits per author
git diff --stat                        # Show file changes summary
git count-objects -v                   # Count objects in repository
```

---

## **⚡ Git Worktree (Multiple Workspaces)**
```sh
git worktree add <path> <branch>     # Create a new working tree
git worktree list                    # List all worktrees
git worktree remove <path>           # Remove a worktree
```

---

## **🔥 How to See ALL Available Commands in Your Git Version**
```sh
git help -a                    # List all available Git commands
git help -g                    # Grouped command list
git help -a | grep '  '        # Plumbing & Porcelain
git <command> --help           # Detailed help for a specific command
```
- Plumbing Commands: Low-level commands used internally by Git.
- Porcelain Commands: High-level user-friendly commands.
  
---

This cheat sheet includes **almost all** Git commands that exist!
