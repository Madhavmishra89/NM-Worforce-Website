# NM Workforce Nexus — GitHub Pages deployment

This repository is configured to serve a static site for the custom domain `nmworkforcenexus.com`.

What I added

- `CNAME` — contains `nmworkforcenexus.com` so GitHub Pages associates the site with your domain.
- `index.html` — placeholder homepage (already committed).

Next steps (you must do these at your domain registrar)

1. Add DNS records for the apex domain (`nmworkforcenexus.com`):
   - Type: A  → 185.199.108.153
   - Type: A  → 185.199.109.153
   - Type: A  → 185.199.110.153
   - Type: A  → 185.199.111.153

2. (Optional) Add `www` subdomain if you want `www.nmworkforcenexus.com` to work:
   - Type: CNAME → Name: `www` Value: `Madhavmishra89.github.io`

3. Wait for DNS propagation (minutes → 24 hours). Then GitHub Pages will validate the domain and provision HTTPS.

4. In your repo on GitHub: Settings → Pages — confirm the Source is `main` branch and `/ (root)` folder. If the site doesn't appear automatically, set it to `gh-pages` branch (if you later use a deploy workflow).

5. After GitHub issues a certificate, enable "Enforce HTTPS" in Pages settings.

If you want a build-and-deploy workflow (for React, Vite, etc.) I can add a GitHub Actions workflow that builds and deploys automatically to GitHub Pages — tell me the build command and output folder (for example `npm run build` → `build`).

Troubleshooting

- If you see a "DNS check failed" error in Pages settings, double-check the A records and that there are no conflicting ALIAS/ANAME records.
- If you want the apex domain to redirect to `www` or vice versa, I can provide additional DNS / HTML solutions.

If you want me to add CI/CD to build/deploy automatically, reply with your build command and publish folder.
