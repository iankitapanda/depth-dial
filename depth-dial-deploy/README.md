# Depth Dial — deploy in ~10 minutes

## 1. Get an Anthropic API key
- Go to https://console.anthropic.com
- Sign up / log in, add a payment method (API usage is billed separately from any Claude subscription, but this demo will cost well under $1 total)
- Create an API key under **Settings → API Keys**, copy it

## 2. Push this folder to GitHub
- Create a new repo on github.com (e.g. `depth-dial`)
- From this folder:
  ```
  git init
  git add .
  git commit -m "Depth Dial MVP"
  git branch -M main
  git remote add origin https://github.com/YOUR_USERNAME/depth-dial.git
  git push -u origin main
  ```

## 3. Deploy on Vercel
- Go to https://vercel.com, sign in with GitHub
- Click **Add New → Project**, select your `depth-dial` repo
- Before deploying, add an environment variable:
  - Name: `ANTHROPIC_API_KEY`
  - Value: (the key you copied in step 1)
- Click **Deploy**

## 4. Done
Vercel gives you a live URL like `https://depth-dial-yourname.vercel.app` — that's your production link for the fellowship submission.

## Notes
- The API key never touches the browser — it's only used inside `api/discover.js`, which runs server-side on Vercel.
- The catalog is a small curated demo set (not live Spotify data) — intentional scoping for a prototype, mention this in your deck.
- Session memory uses `localStorage`, so it persists per-browser but isn't shared across devices.
