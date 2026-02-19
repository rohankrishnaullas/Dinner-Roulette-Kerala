# Dinner Roulette (Kerala)

A single-file roulette spinner for Kerala-style dinner options.

## Open it (quickest)
- Open `index.html` in your browser (double-click).

## Open it on your phone (recommended)
You’ll want a local server so your phone can load it easily.

### Option A: `npx serve` (Node)
From `App/Code`:

```powershell
cd "C:\Users\rohanullas\Downloads\09 Fusion and Kid Buu Sagas ( Updated on 20-07-21 )\App\Code"

# serves on http://localhost:4173
npx --yes serve dinner-roulette -l 4173
```

Then open on your phone (same Wi‑Fi):
- Find your PC’s LAN IP (e.g. `ipconfig`) and open:
  - `http://<YOUR_PC_IP>:4173/`

### Option B: Python
From `App/Code/dinner-roulette`:

```powershell
cd "C:\Users\rohanullas\Downloads\09 Fusion and Kid Buu Sagas ( Updated on 20-07-21 )\App\Code\dinner-roulette"
python -m http.server 4173
```

## Add a GIF at the top
- Replace the placeholder box in `index.html` with an `<img>` tag, or
- Keep the placeholder and just drop a GIF later if you’re hosting it.

## Edit dinner options
- In `index.html`, edit the `options` array (keep it at 15 items if you want equal slices).

## Deploy (Azure Static Web Apps via GitHub Actions)
This folder includes a workflow that deploys the static files (no build step):
- `.github/workflows/azure-static-web-apps.yml`

### Steps
1. Create a GitHub repo (or use an existing one).
2. Push this folder to the repo (ensure the default branch is `main`).
3. In Azure, create or pick an **Azure Static Web App**.
4. Add the SWA deployment token to your GitHub repo:
   - Repo → **Settings** → **Secrets and variables** → **Actions** → **New repository secret**
   - Name: `AZURE_STATIC_WEB_APPS_API_TOKEN`
   - Value: run this locally (PowerShell) to copy the token:
     - `az staticwebapp secrets list -n <SWA_NAME> -g <RESOURCE_GROUP> --query "properties.apiKey" -o tsv`
5. Push any commit to `main` to trigger the deploy.
