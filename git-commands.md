# 🚀 Git Commands Cheatsheet

Быстрый справочник по основным командам Git с примерами и полезными советами.

---

## 📁 **Basic Commands**


# Initialize a new repository
git init

# Clone a repository
git clone <repository-url>

# Check status
git status

# Add files to staging
git add <filename>
git add .          # Add all files
git add -A         # Add all files including deletions



# 💾 Commit Commands
# Create a commit
git commit -m "Your commit message"

# Amend last commit
git commit --amend -m "New message"

# Add files to last commit
git add .
git commit --amend --no-edit

# Empty commit (for CI/CD triggers)
git commit --allow-empty -m "Trigger deployment"


# 🌿 Branch Commands 
# Create and switch to new branch
git checkout -b <branch-name>

# Switch to existing branch
git checkout <branch-name>
git switch <branch-name>     # Newer alternative

# List all branches
git branch -a

# List local branches
git branch

# Delete branch locally
git branch -d <branch-name>

# Force delete branch locally
git branch -D <branch-name>

# Delete branch remotely
git push origin --delete <branch-name>


# 📜 View History
# View commit history
git log

# View compact history
git log --oneline --graph --all

# View history with dates
git log --pretty=format:"%h - %an, %ar : %s"

# View history of specific file
git log --oneline <filename>

# View tags history
git log --tags --simplify-by-decoration --pretty="format:%ai %d"

# Show changes in commits
git log -p

# Search in commits
git log --grep="search term"



#🔀 Moving Changes Between Branches

# Cherry-pick specific commit
git cherry-pick <commit-hash>

# Apply changes from another branch
git checkout <source-branch> -- <file1> <file2>

# Stash changes
git stash                     # Stash changes
git stash save "message"      # Stash with message
git stash list                # List stashes
git stash pop                 # Apply last stash
git stash apply stash@{n}     # Apply specific stash
git stash drop stash@{n}      # Delete specific stash
git stash clear               # Clear all stashes


#☁️ Remote Operations

# Push to remote
git push origin <branch-name>
git push -u origin <branch-name>  # Set upstream

# Pull from remote
git pull origin <branch-name>
git pull --rebase origin <branch-name>

# Fetch updates
git fetch --all
git fetch --prune           # Remove deleted remote branches

# View remotes
git remote -v

# Add remote
git remote add <name> <url>

# Remove remote
git remote remove <name>

# Show remote info
git remote show origin


# 🏷️ Tags

# Create lightweight tag
git tag v1.0.0

# Create annotated tag
git tag -a v1.0.0 -m "Version 1.0.0 release"

# Push tags to remote
git push origin --tags
git push origin v1.0.0      # Push specific tag

# View all tags
git tag -l
git tag -l "v1.*"           # Filter tags

# Delete tag locally
git tag -d v1.0.0

# Delete tag remotely
git push origin --delete v1.0.0

# Checkout tag
git checkout v1.0.0



# 🔧 Configuration

# Set username and email
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Set default editor
git config --global core.editor "code --wait"

# Color output
git config --global color.ui auto

# Set default branch name
git config --global init.defaultBranch main

# View configuration
git config --list
git config --global --list


#❓ Help & Troubleshooting

# Get help on any command
git help <command>
git <command> --help

# Check Git version
git --version

# Show command reference
git help -g

# Debug
git status --verbose
git diff --name-status


#📊 Visual Tools

# Use gitk for GUI
gitk --all

# Use git-gui
git gui

# Show branch tree
git show-branch --all


