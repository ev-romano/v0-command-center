# Deploy v0 Command Center to Vercel

Single static HTML file. No build step, no framework, no config.

## Prerequisites

```bash
# Vercel CLI installed
npm i -g vercel

# Authenticate (opens browser — one-time)
vercel login
```

## Deploy

```bash
# Clone the repo
gh repo clone ev-romano/v0-command-center
cd v0-command-center

# Link to Vercel project (first time only)
vercel link --yes

# Deploy to preview
vercel --yes --prod
```

That's it. You'll get a URL like `https://v0-command-center-*.vercel.app`.

## Update

After editing `index.html`:

```bash
git add index.html
git commit -m "Update command center"
git push
```

If Vercel is connected to the GitHub repo (via dashboard), pushes auto-deploy.
Otherwise, manually redeploy:

```bash
vercel --yes --prod
```

## Connect GitHub for auto-deploy (recommended)

1. Go to https://vercel.com/new
2. Import `ev-romano/v0-command-center`
3. Click Deploy — zero config needed
4. Every push to `main` auto-deploys

## Delete when done

```bash
# Remove Vercel project
vercel rm v0-command-center --yes

# Delete GitHub repo
gh repo delete ev-romano/v0-command-center --yes
```
