# Complete GitHub Setup Guide

## Step 1: Create a GitHub Account (if you don't have one)

1. Go to https://github.com
2. Click "Sign up" in the top right
3. Enter your email, password, and username
4. Verify your email address

## Step 2: Create a New Repository on GitHub

1. Go to https://github.com
2. Click the **"+"** icon in the top right corner
3. Select **"New repository"**
4. Fill in the details:
   - **Repository name**: `trading-analyzer` (or any name you prefer)
   - **Description**: "Smart AI-powered trading analysis tool"
   - **Public** or **Private**: Choose Public (required for free Streamlit hosting)
   - ❌ **DO NOT** check "Add a README file" (we already have one)
   - ❌ **DO NOT** add .gitignore (we already have one)
   - ❌ **DO NOT** choose a license yet
5. Click **"Create repository"**

## Step 3: Install Git on Your Computer

### Windows:
1. Download Git from https://git-scm.com/download/win
2. Run the installer
3. Use default settings (just click "Next")
4. Open "Git Bash" from Start menu

### Mac:
1. Open Terminal (Command + Space, type "Terminal")
2. Type: `git --version`
3. If not installed, it will prompt you to install

### Linux:
```bash
sudo apt-get update
sudo apt-get install git
```

## Step 4: Configure Git (First Time Only)

Open Terminal (Mac/Linux) or Git Bash (Windows) and run:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Replace with your actual name and the email you used for GitHub.

## Step 5: Navigate to Your Project Folder

### Option A: If you downloaded the files to your computer

```bash
# Windows (in Git Bash)
cd /c/Users/YourUsername/Downloads/trading-analyzer

# Mac/Linux
cd ~/Downloads/trading-analyzer
```

### Option B: Create a new folder and add files

```bash
# Create folder
mkdir trading-analyzer
cd trading-analyzer

# Copy/move your files here:
# - trading_analyzer.py
# - requirements.txt
# - README.md
# - DEPLOYMENT.md
# - .gitignore
# - .streamlit folder
```

## Step 6: Initialize Git and Push to GitHub

Now run these commands **one by one**:

```bash
# 1. Initialize git in this folder
git init

# 2. Add all files to git
git add .

# 3. Create your first commit
git commit -m "Initial commit: Smart Trading Analyzer"

# 4. Rename branch to main (GitHub's default)
git branch -M main

# 5. Link to your GitHub repository
# REPLACE with your actual GitHub username and repository name!
git remote add origin https://github.com/YOUR_USERNAME/trading-analyzer.git

# 6. Push to GitHub
git push -u origin main
```

### 🔑 Authentication

When you run `git push`, GitHub will ask for authentication:

**Option 1: Personal Access Token (Recommended)**

1. Go to GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Click "Generate new token (classic)"
3. Give it a name like "Trading Analyzer"
4. Select scopes: ✅ `repo` (all checkboxes under repo)
5. Click "Generate token"
6. **COPY THE TOKEN** (you won't see it again!)
7. When git asks for password, paste the token

**Option 2: GitHub CLI**
```bash
# Install GitHub CLI: https://cli.github.com/
gh auth login
# Follow the prompts
```

## Step 7: Verify Upload

1. Go to your GitHub repository: `https://github.com/YOUR_USERNAME/trading-analyzer`
2. You should see all your files!

## Quick Reference Card

```bash
# After making changes to your code, update GitHub:
git add .
git commit -m "Description of your changes"
git push

# Example:
git add .
git commit -m "Fixed bug in RSI calculation"
git push
```

## Common Issues & Solutions

### Issue 1: "Permission denied"
**Solution**: Set up authentication (see above)

### Issue 2: "Repository not found"
**Solution**: Check you typed the repository URL correctly
```bash
# Remove wrong remote
git remote remove origin

# Add correct one
git remote add origin https://github.com/YOUR_USERNAME/trading-analyzer.git
```

### Issue 3: "Already exists"
**Solution**: The folder already has git initialized
```bash
# Skip 'git init' and continue from 'git add .'
```

### Issue 4: "Nothing to commit"
**Solution**: You're in the wrong folder
```bash
# Check where you are
pwd

# List files
ls -la

# Make sure you see trading_analyzer.py, requirements.txt, etc.
```

## Visual Guide

```
Your Computer                          GitHub
─────────────────                      ─────────────────
trading-analyzer/                      YOUR_USERNAME/
├── trading_analyzer.py                trading-analyzer
├── requirements.txt                   (Repository)
├── README.md              ──push──>   
├── DEPLOYMENT.md
└── .gitignore
```

## Next Steps After Pushing to GitHub

1. ✅ Files are on GitHub
2. ➡️ Go to https://share.streamlit.io
3. ➡️ Follow DEPLOYMENT.md to deploy your app
4. ➡️ Add your Anthropic API key in Streamlit secrets
5. ✅ Your app is live!

## Need Help?

- **GitHub Help**: https://docs.github.com/en/get-started
- **Git Cheat Sheet**: https://education.github.com/git-cheat-sheet-education.pdf
- **Video Tutorial**: Search YouTube for "how to push to github"

## Important Notes

⚠️ **NEVER commit your API key!** The `.gitignore` file prevents this, but always double-check.

✅ **Use Streamlit Secrets** for API keys (covered in DEPLOYMENT.md)

📧 **Email Verification**: Make sure you verify your GitHub email before deploying to Streamlit
