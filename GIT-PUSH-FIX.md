# Fix: Permission denied (info-finerr → mm-aniljambukiya/call)

Git is using **info-finerr**'s saved login, but the repo **mm-aniljambukiya/call** only allows **mm-aniljambukiya** to push.

## Option 1: Use mm-aniljambukiya in the URL (recommended)

This forces Git to ask for **mm-aniljambukiya**'s credentials when you push:

```powershell
cd C:\workspace\other\expo-app
git remote set-url origin https://mm-aniljambukiya@github.com/mm-aniljambukiya/call.git
git push -u origin main
```

When prompted for **password**, use a **Personal Access Token** for **mm-aniljambukiya** (not the GitHub account password):

1. Log in to GitHub as **mm-aniljambukiya**
2. **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)**
3. **Generate new token** → enable **repo**
4. Copy the token and paste it when Git asks for password

---

## Option 2: Clear saved GitHub credentials (Windows)

So Git stops using **info-finerr** and asks again:

1. Press **Win + S**, type **Credential Manager**, open it
2. **Windows Credentials** → find **git:https://github.com**
3. Click it → **Remove**
4. In a terminal:

   ```powershell
   cd C:\workspace\other\expo-app
   git push -u origin main
   ```

5. When prompted, sign in as **mm-aniljambukiya** (username) and use that account’s **Personal Access Token** as the password

---

## Don’t run `git remote add origin` again

`origin` is already set. Use **set-url** if you need to change it:

```powershell
git remote set-url origin https://mm-aniljambukiya@github.com/mm-aniljambukiya/call.git
```
