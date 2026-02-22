# 🧠 Mindo AI — GitHub Pages Deployment

> A production-ready AI chat app that runs entirely on GitHub Pages using your own Anthropic API key.

---

## 🚀 Deploy in 4 Steps

### Step 1 — Create a GitHub Repository
1. Go to [github.com/new](https://github.com/new)
2. Name it `mindo-ai` (or anything you like)
3. Set it to **Public** (required for free GitHub Pages)
4. Click **Create repository**

### Step 2 — Upload these files
**Option A: GitHub Web UI (easiest)**
1. In your new repo, click **"uploading an existing file"**
2. Drag and drop ALL files from this zip (maintaining the folder structure)
3. Commit with message: `Initial deploy`

**Option B: Git CLI**
```bash
cd mindo-ai-github
git init
git add .
git commit -m "Initial deploy"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/mindo-ai.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages
1. Go to your repo → **Settings** → **Pages** (left sidebar)
2. Under **Source**, select **GitHub Actions**
3. The workflow will trigger automatically on your next push

Your site will be live at:
**`https://YOUR_USERNAME.github.io/mindo-ai/`**

(Takes ~60 seconds after first push)

### Step 4 — Get & Enter Your API Key
1. Go to [console.anthropic.com](https://console.anthropic.com) → sign up free
2. Navigate to **API Keys** → **Create Key** → copy it
3. Open your live Mindo AI site
4. Sign in with any email/password
5. A modal will appear — paste your key (starts with `sk-ant-...`)
6. Click **Connect & Start Chatting** ✓

---

## 🔒 How API Key Security Works

Since GitHub Pages is static (no server), your key is handled carefully:

| What we do | What we don't do |
|---|---|
| ✅ Key stored in JavaScript memory only | ❌ Never written to localStorage |
| ✅ Cleared when you close the tab | ❌ Never sent to any third party |
| ✅ Never appears in network logs | ❌ Never committed to your repo |
| ✅ Cleared from input field immediately | ❌ Never stored in cookies |

**Bottom line**: Your key lives only in your browser's RAM for the duration of the session. Closing the tab clears it completely.

---

## 🗂 File Structure

```
mindo-ai/
├── index.html                    # Full Mindo AI application
├── .github/
│   └── workflows/
│       └── deploy.yml            # Auto-deploy to GitHub Pages
└── README.md
```

---

## 💡 Tips

- **Custom domain**: Settings → Pages → Custom domain → enter `chat.yourdomain.com`
- **Update the app**: Edit `index.html`, push to `main` — auto-deploys in ~30s
- **Change AI model**: Search `claude-sonnet-4-20250514` in `index.html` and swap it
- **Change the system prompt**: Search `You are Mindo AI` in `index.html`

---

## 💰 Cost

- GitHub Pages hosting: **Free**
- Anthropic API: Pay-as-you-go (~$3/million input tokens with claude-sonnet)
- Typical light usage: **< $1/month**
