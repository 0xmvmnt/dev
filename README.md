# Superpower Docs — Mintlify Setup Guide

## Quick Start (5 minutes)

### 1. Create a Mintlify Account
- Go to [mintlify.com](https://mintlify.com) and sign up
- Click "Start for free" — the free tier works fine to start

### 2. Create a GitHub Repo
- Create a new repo on GitHub (e.g. `superpower-docs`)
- Push this entire folder to the repo:
  ```bash
  git init
  git add .
  git commit -m "Initial litepaper"
  git remote add origin https://github.com/YOUR_ORG/superpower-docs.git
  git push -u origin main
  ```

### 3. Connect to Mintlify
- In the Mintlify dashboard, click "New Project"
- Connect your GitHub account
- Select the `superpower-docs` repo
- Mintlify will auto-detect `mint.json` and deploy

### 4. Customize Before Going Live

#### Replace placeholders in `mint.json`:
- `YOUR_INVITE` → Your Discord invite link
- `YOUR_HANDLE` → Your X/Twitter handle
- `YOUR_ORG` → Your GitHub org name

#### Add your logo:
- Drop your logo files into `/images/`:
  - `logo-dark.svg` (for dark backgrounds)
  - `logo-light.svg` (for light backgrounds)
  - `favicon.svg`

#### Update brand colors:
- Edit the `colors` section in `mint.json`
- Current defaults are purple (#7C3AED) — change to match your brand

#### Update CTA links:
- Search for `href="#"` across the `.mdx` files
- Replace with your actual links (app, docs, community)

### 5. Custom Domain (Later)
- In Mintlify dashboard → Settings → Custom Domain
- Add your domain (e.g. `docs.superpower.xyz`)
- Point a CNAME record to Mintlify's servers (they'll give you the value)

---

## File Structure

```
superpower-docs/
├── mint.json                              # Mintlify configuration
├── images/                                # Logo & favicon (add yours)
├── litepaper/
│   ├── what-is-superpower.mdx            # Introduction
│   ├── the-missing-economic-layer.mdx    # Problem statement
│   ├── the-protocol.mdx                  # Protocol architecture
│   ├── the-power-token.mdx               # $POWER token economy
│   ├── skills.mdx                        # Skills interface
│   ├── orchestration.mdx                 # Workflow composition
│   ├── prolly.mdx                        # First flagship Skill
│   ├── beyond-prediction-markets.mdx     # Expansion roadmap
│   ├── why-participate-now.mdx           # Call to action
│   └── the-vision.mdx                    # Closing vision
└── README.md                             # This file
```

## Adding More Pages Later

1. Create a new `.mdx` file in the appropriate folder
2. Add the page path to `mint.json` under `navigation`
3. Push to GitHub — Mintlify auto-deploys on push

## Mintlify Components Used

- `<Steps>` — Numbered step flows (Skills lifecycle, Prolly flow)
- `<Card>` / `<CardGroup>` — Feature cards (Protocol pillars, token channels)
- `<Note>` — Highlighted callout boxes
- `<Info>` — Informational callouts
- `<Tip>` — Tip callouts
- Tables — Standard markdown tables

Full component docs: [mintlify.com/docs/content/components](https://mintlify.com/docs/content/components)
