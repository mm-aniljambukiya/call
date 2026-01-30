# Fix Git remote and push

## 1. You don't need to add origin again

`origin` is already set to `https://github.com/mm-aniljambukiya/expo-app.git`.  
If you ever need to change it:

```powershell
git remote set-url origin https://github.com/mm-aniljambukiya/expo-app.git
```

## 2. Fix "Repository not found"

This usually means the repo **doesn't exist on GitHub** or you don't have access.

### Option A: Create the repo on GitHub first

1. Open **https://github.com/new**
2. Sign in as **mm-aniljambukiya** (or the account you want).
3. Set **Repository name** to: `expo-app`
4. Choose **Public** (or Private).
5. **Do not** add a README, .gitignore, or license (you already have local files).
6. Click **Create repository**.

Then push:

```powershell
cd C:\workspace\other\expo-app
git push -u origin main
```

### Option B: Repo exists but under a different name/account

Update the remote URL to the correct one:

```powershell
git remote set-url origin https://github.com/CORRECT-USERNAME/CORRECT-REPO-NAME.git
git push -u origin main
```

### Option C: Authentication (HTTPS)

GitHub no longer accepts account passwords for `git push`. Use a **Personal Access Token**:

1. GitHub → **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)**.
2. **Generate new token**, enable at least **repo**.
3. Copy the token.
4. When you run `git push`, use the token as the **password** (username = your GitHub username).

Or use **SSH** instead of HTTPS:

```powershell
git remote set-url origin git@github.com:mm-aniljambukiya/expo-app.git
git push -u origin main
```

(You need an SSH key added to your GitHub account.)
