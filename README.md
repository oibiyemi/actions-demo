# Initialize git locally
git init

# Create the repository on GitHub using the gh CLI
# Replace 'my-first-action' with your desired repository name
# The '-c' flag creates it as a public repository
# The '-d' flag sets the description
gh repo create actions-demo --public -d "First GitHub Actions demo for VS Code"

# Add the remote URL (gh repo create does this automatically, but confirm)
# You can check with 'git remote -v'

# Create an initial commit
echo "# GitHub Actions Demo" > README.md
git add .
git commit -m "Initial commit for Actions setup"

# Push the main branch to GitHub
git branch -M main
git remote set-url origin https://github.com/oibiyemi/actions-demo.git
git push -u origin main