# **📝 Git Cheat Sheet: The Ultimate Guide**  
_Last Updated: 2025_

## **📌 Basic Configuration**
```sh
git config --global user.name "Your Name"      # Set user name
git config --global user.email "you@example.com" # Set email
git config --global color.ui auto              # Enable colored output
git config --global core.editor nano           # Set default editor
git config --global core.autocrlf true         # Auto handle line endings
git config --list                              # List all configuration
```

---

## **📁 Repository Setup**
```sh
git init                        # Initialize a new repository
git clone <repo_url>            # Clone an existing repository
git remote add origin <url>     # Add remote repository
git remote -v                   # View remote repositories
git remote remove <name>        # Remove remote repository
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
git push -u origin <branch>     # Push and track upstream
git push --force                # Force push (use with caution)
git pull origin <branch>        # Pull latest changes
git fetch                       # Fetch changes without merging
git fetch --prune               # Fetch and remove deleted remote branches
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
git reset --soft HEAD~1         # Undo commit (keep changes staged)
git reset --mixed HEAD~1        # Undo commit (keep changes unstaged)
git reset --hard HEAD~1         # Undo commit & discard changes
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
git tag                         # List all tags
git tag <tagname>               # Create a new tag
git tag -a <tagname> -m "msg"   # Create annotated tag
git push origin <tagname>       # Push a tag
git push --tags                 # Push all tags
git tag -d <tagname>            # Delete local tag
git push origin --delete <tagname> # Delete remote tag
```

---

## **💣 Deleting & Cleaning**
```sh
git rm <file>                   # Remove file from repo & working dir
git rm --cached <file>          # Remove from repo but keep locally
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
git credential-cache exit            # Clear cached credentials
git credential reject https://github.com
git credential approve https://github.com
```

---

## **🌎 Working with Submodules**
```sh
git submodule add <repo_url>         # Add submodule
git submodule update --init --recursive # Clone/update submodules
git submodule foreach git pull origin main # Update all submodules
git submodule deinit -f --all         # Remove all submodules
```

---

## **🧪 Advanced Git Features**
```sh
git bisect start                     # Start binary search for bugs
git bisect bad                        # Mark current commit as bad
git bisect good <commit>              # Mark commit as good
git bisect reset                      # End bisect session
```

---

## **📦 Working with Large Files**
```sh
git lfs install                       # Install Git LFS
git lfs track "*.zip"                 # Track large files
git add .gitattributes                 # Add LFS config
git lfs migrate import --everything --include="*.zip" # Migrate existing files
```

---

## **🐳 Working with Aliases**
```sh
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.st status
git config --global alias.last "log -1 HEAD"
```

---

## **📊 Viewing Statistics**
```sh
git shortlog -sn                      # Show commits per author
git diff --stat                        # Show file changes summary
git count-objects -v                   # Count objects in repository
```

---

This cheat sheet includes **almost all** Git commands that exist!
