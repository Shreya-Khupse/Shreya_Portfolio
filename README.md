# Shreya Khupse — Portfolio

A modern, responsive personal portfolio for **Shreya Khupse** (IT Student | AI & Web Developer), built with **React**, **Vite**, and **Tailwind CSS**. Suitable for internships, placements, and higher studies (MBA / MS / AI roles).

## Tech Stack

- **React 18** + **Vite 5**
- **Tailwind CSS 3**
- No backend (contact form is UI-only)

## Project Structure

```
src/
├── components/
│   ├── Navbar.jsx    # Fixed nav with mobile menu
│   ├── Hero.jsx      # Hero with CTAs
│   ├── About.jsx     # About me
│   ├── Skills.jsx    # Skills (Programming, Web, AI/ML, Tools)
│   ├── Projects.jsx  # Project cards
│   ├── Contact.jsx   # Contact info + form (UI only)
│   └── Footer.jsx    # Footer with links
├── App.jsx
├── main.jsx
└── index.css
```

## Run Locally

1. **Install dependencies**

   ```bash
   npm install
   ```

2. **Start dev server**

   ```bash
   npm run dev
   ```

   Open [http://localhost:5173](http://localhost:5173) in your browser.

3. **Production build**

   ```bash
   npm run build
   ```

   Output is in `dist/`. Preview with:

   ```bash
   npm run preview
   ```

## Deploy

### Vercel

1. Push this repo to GitHub.
2. Go to [vercel.com](https://vercel.com) and sign in with GitHub.
3. **Import** the repository and deploy (Vercel auto-detects Vite).
4. Optional: set root directory to this folder if the repo has multiple projects.

### GitHub Pages

1. Install the GitHub Pages plugin (e.g. `gh-pages`):

   ```bash
   npm install -D gh-pages
   ```

2. In `package.json`, add a `homepage` and a deploy script (use your GitHub username and repo name):

   ```json
   "homepage": "https://<username>.github.io/<repo-name>",
   "scripts": {
     "deploy": "vite build && gh-pages -d dist"
   }
   ```

3. In `vite.config.js`, set `base` to your repo name if the site is at `https://<username>.github.io/<repo-name>/`:

   ```js
   base: '/<repo-name>/',
   ```

4. Build and deploy:

   ```bash
   npm run deploy
   ```

   Enable GitHub Pages in the repo **Settings → Pages**, source: **Deploy from a branch**, branch: **gh-pages**, folder: **/ (root)**.

## Sections

- **Hero** — Name, role, tagline, “View Projects” & “Contact Me” buttons  
- **About** — Short intro (AI, ML, Web Dev, real-world projects, internships/placements)  
- **Skills** — Programming, Web, AI/ML, Tools  
- **Projects** — Career.AI, AI Attendance, Ecommerce Dashboard, Transport Management, ADmyBRAND Insights  
- **Contact** — Email, GitHub, mobile + UI-only contact form  

## Customization

- **Personal details**: Update `Hero.jsx`, `Contact.jsx`, `Footer.jsx`, and `index.html` (title, meta).
- **Colors**: Edit `tailwind.config.js` under `theme.extend.colors.primary`.
- **Projects**: Edit the `projects` array in `src/components/Projects.jsx`.

## License

Private portfolio. All rights reserved.
