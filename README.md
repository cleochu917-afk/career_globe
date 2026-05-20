# Your Path Globe — Deployment

## Deploy to Vercel

### 1. Push to GitHub
```bash
git init
git add .
git commit -m "Your Path Globe"
git remote add origin https://github.com/YOUR_USERNAME/your-path-globe.git
git push -u origin main
```

### 2. Connect to Vercel
1. Go to [vercel.com](https://vercel.com) → New Project
2. Import your GitHub repo
3. Framework Preset: **Other**
4. No build command needed — it's a static file

### 3. Add your API key
In Vercel dashboard → Project → Settings → Environment Variables:
```
ANTHROPIC_API_KEY = sk-ant-...your key here...
```

### 4. Deploy
Vercel deploys automatically on every push to main.

---

## File structure
```
career_globe.html   — the entire app
api/claude.js       — serverless proxy (keeps API key server-side)
vercel.json         — routing config
```

## Local development
```bash
npx vercel dev
```
Then open http://localhost:3000

The `vercel dev` command runs the serverless function locally so the proxy works.
You'll need a `.env.local` file:
```
ANTHROPIC_API_KEY=sk-ant-...
```
