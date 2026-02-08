# Step-by-Step: Push This Project to GitHub

Use these steps to upload your **Shreya Portfolio** project to your repo **Shreya_Portfolio**.

---

## Prerequisites

- **Git** installed on your PC. Check by opening PowerShell and typing:
  ```powershell
  git --version
  ```
  If it’s not installed, download from [git-scm.com](https://git-scm.com/).

- A **GitHub account** and a **new empty repository** named `Shreya_Portfolio`.
  - Go to [github.com](https://github.com) → **+** → **New repository**
  - Repository name: **Shreya_Portfolio**
  - Set to **Public**
  - Do **not** add a README, .gitignore, or license (you already have them)
  - Click **Create repository**

---

## Steps (run in PowerShell)

Open PowerShell and run each block **one at a time** from the project folder.

### Step 1: Go to your project folder

```powershell
cd "c:\Users\shrey\OneDrive\Desktop\Shreya Portfolio"
```

### Step 2: Initialize Git (only if this folder is not already a git repo)

```powershell
git init
```

If you see "Reinitialized existing Git repository", that’s fine.

### Step 3: Add all files

This adds everything except what’s in `.gitignore` (e.g. `node_modules`, `dist`).

```powershell
git add .
```

### Step 4: Create the first commit

```powershell
git commit -m "Initial commit - Shreya Portfolio"
```

### Step 5: Name the main branch (optional but recommended)

```powershell
git branch -M main
```

### Step 6: Add your GitHub repo as “origin”

Replace **Shreya-Khupse** with your GitHub username if it’s different:

```powershell
git remote add origin https://github.com/Shreya-Khupse/Shreya_Portfolio.git
```

If you see “remote origin already exists”, use this instead to update the URL:

```powershell
git remote set-url origin https://github.com/Shreya-Khupse/Shreya_Portfolio.git
```

### Step 7: Push to GitHub

```powershell
git push -u origin main
```

- The first time, GitHub may ask you to sign in (browser or username/password/token).
- If you use **two-factor authentication**, you must use a **Personal Access Token** instead of your password. Create one at: GitHub → **Settings** → **Developer settings** → **Personal access tokens**.

---

## Done

Refresh your repo on GitHub. You should see all project files (except `node_modules` and `dist`).

**Later, when you change something and want to update GitHub:**

```powershell
cd "c:\Users\shrey\OneDrive\Desktop\Shreya Portfolio"
git add .
git commit -m "Describe your changes"
git push
```
