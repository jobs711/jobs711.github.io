```markdown
# GitHub Pages + Custom Domain

This repository contains a minimal static website for GitHub Pages.

Files:
- `index.html` — site entry
- `CNAME` — contains the custom domain (replace `example.com`)

How to publish
1. Replace `CNAME` contents with your custom domain (for example `example.com` or `www.example.com`) if needed.
2. Commit and push these files to your repository (recommended branch: `main`).
3. In GitHub: Repository → Settings → Pages:
   - Source: choose the branch (`main`) and folder (`/ (root)`).
   - Save. GitHub will publish the site at `https://<owner>.github.io/<repo>` (temporary) or your custom domain once DNS points.
4. After DNS is correct, in the same Pages settings, set the custom domain (if not auto-filled) and check "Enforce HTTPS" once enabled.

DNS configuration examples
- Apex domain (example.com) — set these A records:
  - 185.199.108.153
  - 185.199.109.153
  - 185.199.110.153
  - 185.199.111.153

- Subdomain (www.example.com or docs.example.com) — add:
  - Type: CNAME
  - Name: www (or docs)
  - Value: <your-github-username>.github.io

Notes and tips
- DNS changes can take from a few minutes to 48 hours to propagate.
- GitHub will provision HTTPS automatically after DNS points and verification completes.
- If your DNS provider supports ALIAS/ANAME, you can point the apex directly to `<your-github-username>.github.io`. Otherwise use the 4 A records above for the apex.
- If you prefer the site served from the `gh-pages` branch, or want a build pipeline (Jekyll/React/Vite), I can add a GitHub Actions workflow to build and deploy; tell me which.
- If you'd like, I can create the repo and push these files for you — tell me repo owner/name and the custom domain to put into CNAME.

Troubleshooting
- If HTTPS is stuck: double-check DNS records and remove any conflicting A/CNAME entries. Wait an hour and re-check Pages settings.
- If GitHub Pages shows a 404: confirm branch/folder selected in Pages settings and that `index.html` is at the selected location.
```
