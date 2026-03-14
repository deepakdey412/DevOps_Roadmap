\# Install Git

sudo apt update && sudo apt install git -y # Ubuntu/Debian

brew install git # Mac

git --version # Check installed Git version

\# Configure Git

git config --global user.name "Your Name" # Set Git username

git config --global user.email "you@example.com" # Set Git email

\# Initialize Local Repository

mkdir MyProject

cd MyProject

git init # Initialize Git in folder

\# Check Status

git status # Check changes in repo

\# Stage Changes

git add . # Add all files to staging

git add filename # Add specific file

\# Commit Changes

git commit -m "Commit message" # Commit staged changes

\# Link Local Repo to GitHub

git remote add origin https://github.com/username/repo.git

\# Push Changes to GitHub

git branch -M main # Rename branch to main

git push -u origin main # Push local commits

\# Pull Changes from GitHub

git pull origin main # Fetch and merge updates

\# Clone Repository

git clone https://github.com/username/repo.git

\# Branching

git branch new-feature # Create new branch

git checkout new-feature # Switch to branch

git merge new-feature # Merge branch into main

\# Updating Repo After Changes

git add .

git commit -m "Added new feature"

git push