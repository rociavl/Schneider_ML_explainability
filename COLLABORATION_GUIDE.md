# Collaboration Guide - Schneider ML Explainability Challenge

This guide will help you and your team collaborate effectively on this repository.

## Table of Contents
- [Initial Setup](#initial-setup)
- [Forking the Repository](#forking-the-repository)
- [Cloning Your Fork](#cloning-your-fork)
- [Setting Up the Environment](#setting-up-the-environment)
- [Making Changes](#making-changes)
- [Committing Your Work](#committing-your-work)
- [Pushing Changes](#pushing-changes)
- [Creating a Pull Request](#creating-a-pull-request)
- [Keeping Your Fork Updated](#keeping-your-fork-updated)
- [Best Practices](#best-practices)

---

## Initial Setup

### Prerequisites
- Git installed on your computer
- GitHub account
- Conda/Miniconda installed

---

## Forking the Repository

1. **Go to the main repository:**
   - Visit: `https://github.com/rociavl/Schneider_ML_explainability`

2. **Fork the repository:**
   - Click the "Fork" button in the top-right corner
   - This creates a copy of the repository under your GitHub account
   - Your fork will be at: `https://github.com/YOUR_USERNAME/Schneider_ML_explainability`

---

## Cloning Your Fork

1. **Clone your fork to your local machine:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/Schneider_ML_explainability.git
   ```

2. **Navigate to the repository:**
   ```bash
   cd Schneider_ML_explainability
   ```

3. **Add the original repository as upstream:**
   ```bash
   git remote add upstream https://github.com/rociavl/Schneider_ML_explainability.git
   ```

4. **Verify your remotes:**
   ```bash
   git remote -v
   ```
   You should see:
   - `origin` → your fork
   - `upstream` → original repository

---

## Setting Up the Environment

1. **Create the conda environment:**
   ```bash
   conda create -n challenge_datathon python=3.11 -y
   ```

2. **Activate the environment:**
   ```bash
   conda activate challenge_datathon
   ```

3. **Install required packages:**
   ```bash
   # Install common data science packages
   conda install pandas numpy scikit-learn matplotlib seaborn jupyter -y

   # Install additional packages as needed
   pip install -r requirements.txt  # if requirements.txt exists
   ```

---

## Making Changes

1. **Always create a new branch for your work:**
   ```bash
   git checkout -b feature/your-feature-name
   ```

   Branch naming conventions:
   - `feature/feature-name` - for new features
   - `fix/bug-description` - for bug fixes
   - `docs/update-description` - for documentation
   - `experiment/model-name` - for experimental work

2. **Make your changes:**
   - Edit files, create notebooks, add code
   - Test your changes

---

## Committing Your Work

1. **Check what files you've changed:**
   ```bash
   git status
   ```

2. **Add files to staging:**
   ```bash
   # Add specific files
   git add path/to/file.py

   # Or add all changes
   git add .
   ```

3. **Commit your changes:**
   ```bash
   git commit -m "Brief description of what you changed"
   ```

   **Good commit message examples:**
   - `"Add initial data exploration notebook"`
   - `"Fix bug in preprocessing pipeline"`
   - `"Update README with installation instructions"`
   - `"Implement SHAP explainability analysis"`

4. **Make multiple commits for different logical changes:**
   ```bash
   git add notebook.ipynb
   git commit -m "Add exploratory data analysis"

   git add preprocessing.py
   git commit -m "Create data preprocessing module"
   ```

---

## Pushing Changes

1. **Push your branch to your fork:**
   ```bash
   git push origin feature/your-feature-name
   ```

2. **If it's your first push on this branch:**
   ```bash
   git push -u origin feature/your-feature-name
   ```

---

## Creating a Pull Request

1. **Go to your fork on GitHub:**
   - Visit: `https://github.com/YOUR_USERNAME/Schneider_ML_explainability`

2. **Create a Pull Request:**
   - Click "Compare & pull request" button (appears after pushing)
   - Or go to "Pull requests" tab → "New pull request"

3. **Fill in PR details:**
   - **Title:** Brief description of your changes
   - **Description:**
     - What changes you made
     - Why you made them
     - Any testing you did
     - Screenshots/results if applicable

4. **Submit the PR:**
   - Click "Create pull request"
   - Wait for review from team members
   - Address any feedback or requested changes

---

## Keeping Your Fork Updated

**Important:** Always sync with the main repository before starting new work!

1. **Fetch updates from upstream:**
   ```bash
   git fetch upstream
   ```

2. **Switch to your main branch:**
   ```bash
   git checkout main
   ```

3. **Merge upstream changes:**
   ```bash
   git merge upstream/main
   ```

4. **Push updates to your fork:**
   ```bash
   git push origin main
   ```

---

## Best Practices

### Communication
- 💬 Communicate with your team before starting major work
- 📝 Use clear, descriptive commit messages
- 🔍 Review each other's pull requests
- 💡 Ask questions if you're unsure

### Code Organization
- 📁 Keep notebooks in a `notebooks/` folder
- 🐍 Keep Python scripts in a `src/` or `scripts/` folder
- 📊 Keep results/figures in a `results/` or `outputs/` folder
- 📄 Document your code with comments and docstrings

### Git Workflow
- ✅ Always pull latest changes before starting work
- 🌿 Create a new branch for each feature/task
- 💾 Commit frequently with meaningful messages
- 🔄 Keep pull requests focused and small
- 🧪 Test your code before committing

### Avoiding Conflicts
- 📢 Announce what you're working on to avoid duplicate work
- 🔄 Sync with upstream regularly
- 📦 Don't commit large data files (use `.gitignore`)
- 🔧 Don't commit environment-specific files

### File Management
**DO commit:**
- Source code (`.py`, `.ipynb`)
- Documentation (`.md`)
- Configuration files
- Small sample datasets

**DON'T commit:**
- Large datasets (use `.gitignore`)
- Model files (`.h5`, `.pkl` - unless small)
- Virtual environments
- IDE-specific files
- Temporary files

---

## Common Commands Reference

```bash
# Check status
git status

# Create and switch to new branch
git checkout -b branch-name

# Switch branches
git checkout branch-name

# Add changes
git add .

# Commit changes
git commit -m "message"

# Push to your fork
git push origin branch-name

# Pull latest changes
git pull origin main

# Sync with upstream
git fetch upstream
git merge upstream/main

# View commit history
git log

# View remotes
git remote -v
```

---

## Troubleshooting

### Merge Conflicts
If you encounter merge conflicts:
1. Open the conflicting files
2. Look for conflict markers: `<<<<<<<`, `=======`, `>>>>>>>`
3. Resolve conflicts by choosing which changes to keep
4. Remove conflict markers
5. Add and commit the resolved files

### Accidentally Committed to Wrong Branch
```bash
# Undo last commit (keeps changes)
git reset --soft HEAD~1

# Switch to correct branch
git checkout correct-branch

# Add and commit again
git add .
git commit -m "message"
```

### Need to Discard Local Changes
```bash
# Discard changes to specific file
git checkout -- filename

# Discard all local changes (be careful!)
git reset --hard HEAD
```

---

## Questions or Issues?

If you run into problems:
1. Check this guide first
2. Search online for the error message
3. Ask your teammates
4. Check Git documentation: https://git-scm.com/doc

---

**Happy collaborating! Let's build something great together! 🚀**
