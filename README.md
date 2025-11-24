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

# Create the necessary directory structure
mkdir -p .github/workflows

# Create a sample YAML workflow file using the 'touch' command
touch .github/workflows/ci-demo.yml

# Open the new file in VS Code for editing
code .github/workflows/ci-demo.yml



name: Simple Greeting

on: [push]

jobs:
  greet:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v4
      
      - name: Display Message
        run: echo "Hello, GitHub Actions is running successfully!"
      
      - name: Check Branch
        run: |
          echo "This job runs on the ${{ github.ref_name }} branch."