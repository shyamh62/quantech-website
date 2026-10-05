https://shyamh62.github.io/quantech-website/

### Using a GitHub Personal Access Token (PAT)

If Obsidian asks for credentials or fails to connect, GitHub no longer accepts account passwords for Git operations. You'll need a Personal Access Token:

#### Step 1: Generate a Token on GitHub

1. Log into [GitHub.com](https://github.com/) and click on profile pic -> go to **Settings → Developer Settings → Personal access tokens → Tokens (classic)**.
    
2. Click **Generate new token (classic)**.
    
3. Give it a note (e.g., `Obsidian Sync`) and set an expiration date.
    
4. Select the **`repo`** scope checkbox (this gives it permission to push to your repository).
    
5. Click **Generate token** at the bottom, and **copy the token immediately** (you won't see it again).
    

#### Step 2: Connect it via Terminal on Mac

*Open **Terminal** on your Mac and run these commands to store your credentials globally: (only first time) token dan qt

Bash

```
# Set your name and email for commits
git config --global user.name "Your Name"
git config --global user.email "your-github-email@example.com"

# Tell Git to save your credentials in macOS Keychain
git config --global credential.helper osxkeychain
```

Next, navigate to your vault folder in Terminal and run a quick test command:

Bash

```
cd /path/to/your/website-vault
git pull
```

When macOS prompts you for your password in Terminal, **paste your Personal Access Token** instead of your GitHub password. Mac Keychain will save it permanently, and Obsidian Git will use it automatically from then on.