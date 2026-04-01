# AI-Healthcheck — One-Time GitHub Setup

Run these commands once to initialize the repo and enable GitHub Pages.

## Step 1: Push this folder to GitHub

```bash
cd ~/Documents/Claude/PROFESSIONAL/SE_Workspace/AI-Healthcheck
git init
git add .
git commit -m "Initial setup — AI Health Check reports"
git branch -M main
git remote add origin https://github.com/nveer/AI-Healthcheck.git
git push -u origin main
```

## Step 2: Enable GitHub Pages

1. Go to https://github.com/nveer/AI-Healthcheck/settings/pages
2. Under **Source**, select **GitHub Actions**
3. Save

After the first push, the GitHub Actions workflow (`.github/workflows/pages.yml`) will auto-deploy. Your index page will be live at:
`https://nveer.github.io/AI-Healthcheck/`

## Step 3: Install updated plugin

Install `jackie-pages-v2.plugin` from:
`~/Documents/Claude/PROFESSIONAL/SE_Workspace/outputs/jackie-pages-v2.plugin`

This replaces the previous jackie-pages plugin (v0.1.0 → v0.2.0) with HTML health report output + auto-push to this repo.

## How reports get published

Every time you run `/jackie-pages:account-summary [account-id]`, the command will:
1. Pull analytics from Studio
2. Generate a branded HTML health report
3. Save it to `AI-Healthcheck/reports/[account-slug]-health-report.html`
4. Run `git commit && git push` automatically
5. Report goes live at `https://nveer.github.io/AI-Healthcheck/reports/[account-slug]-health-report.html`
6. That URL is embedded in the outreach email draft
