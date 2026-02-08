# Step-by-Step Deployment Guide

Choose **one** of the options below. **Vercel** is the quickest; **GitHub Pages** is free and keeps everything on GitHub.

---

## Option A: Deploy with Vercel (recommended)

### Step 1: Put your project on GitHub

1. Open [github.com](https://github.com) and sign in.
2. Click the **+** (top right) → **New repository**.
3. Set:
   - **Repository name:** `Shreya_Portfolio` (or your choice)
   - **Public**
   - Leave "Add a README" **unchecked** (you already have one).
4. Click **Create repository**.
5. On your computer, open PowerShell in your portfolio folder and run (replace `YOUR_USERNAME` and `YOUR_REPO` with your GitHub username and repo name):

   ```powershell
   cd "c:\Users\shrey\OneDrive\Desktop\Shreya Portfolio"
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```

   Example for user **Shreya-Khupse** and repo **Shreya_Portfolio**:

   ```powershell
   git remote add origin https://github.com/Shreya-Khupse/Shreya_Portfolio.git
   git push -u origin main
   ```

### Step 2: Deploy on Vercel

1. Go to [vercel.com](https://vercel.com) and sign in (choose **Continue with GitHub**).
2. Click **Add New…** → **Project**.
3. **Import** the repository you just created (e.g. `Shreya_Portfolio`). Click **Import**.
4. Leave settings as they are (Vercel detects Vite automatically):
   - **Framework Preset:** Vite  
   - **Root Directory:** . (leave default)  
   - **Build Command:** `npm run build`  
   - **Output Directory:** `dist`
5. Click **Deploy**.
6. Wait 1–2 minutes. When it’s done, click **Visit** to open your live site.

Your site will be at: `https://your-project-name.vercel.app` (you can change the name in Project Settings).

---

## Option B: Deploy with GitHub Pages

### Step 1: Create the repo and push (same as Vercel Step 1)

1. Create a new **public** repository on GitHub (e.g. `Shreya_Portfolio`).
2. In PowerShell, from your portfolio folder:

   ```powershell
   cd "c:\Users\shrey\OneDrive\Desktop\Shreya Portfolio"
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```

   Replace `YOUR_USERNAME` and `YOUR_REPO` with your GitHub username and repository name.

### Step 2: Install gh-pages and add deploy script

In the same folder, run:

```powershell
npm install -D gh-pages
```

Then we need to add two things to `package.json`:

- **homepage** (so assets load correctly). Already set to:
  - `https://Shreya-Khupse.github.io/Shreya_Portfolio/`
- A **deploy** script: `"deploy": "vite build && gh-pages -d dist"` (already in package.json)

**Note:** This project is already configured for **Shreya_Portfolio**. If your GitHub username or repo name is different, edit `homepage` in `package.json` to match.

### Step 3: (Optional) Edit package.json

Only if your repo or username is different: open `package.json` and change the `homepage` value to `https://YOUR_USERNAME.github.io/YOUR_REPO/`.

### Step 4: Set base path in Vite

Open `vite.config.js`. The `base` is already set to `/Shreya_Portfolio/` for your repo. If you used a different repo name, change it to match (e.g. `base: '/Your_Repo_Name/',`).

### Step 5: Deploy to GitHub Pages

Run:

```powershell
npm run deploy
```

This builds the site and pushes the `dist` folder to a branch named `gh-pages`.

### Step 6: Turn on GitHub Pages

1. On GitHub, open your repository.
2. Go to **Settings** → **Pages** (left sidebar).
3. Under **Build and deployment**:
   - **Source:** Deploy from a branch
   - **Branch:** `gh-pages` → **/ (root)** → **Save**
4. Wait 1–2 minutes. Your site will be at:

   **https://Shreya-Khupse.github.io/Shreya_Portfolio/**  
   (replace with your username if different.)

---

## After deployment

- **Vercel:** You get a URL like `https://shreya-portfolio.vercel.app`. You can add a custom domain in Project Settings.
- **GitHub Pages:** You get `https://<username>.github.io/<repo-name>/`.

Every time you make changes:

- **Vercel:** Push to `main`; Vercel will redeploy automatically.
- **GitHub Pages:** Run `npm run deploy` again, then push if you use a separate branch for code.

If something doesn’t work, double-check:

- **Vercel:** Build command is `npm run build`, output directory is `dist`.
- **GitHub Pages:** `homepage` in package.json and `base` in `vite.config.js` must match your repo name (e.g. `Shreya_Portfolio`) with a trailing slash.
