# Static website on AWS Amplify

## Structure

```
.
├── index.html
├── 404.html
├── css/style.css
├── js/main.js
├── amplify.yml        # Amplify build settings (no build step)
└── customHttp.yml     # Security and cache headers
```

## Deploy

1. Push this repo to GitHub.
2. AWS Console > AWS Amplify > Create new app > Host web app > GitHub.
3. Authorize GitHub, then pick the repo and branch (for example `main`).
4. Amplify detects `amplify.yml`. Leave the settings as they are and choose Save and deploy.
5. Open the `https://<branch>.<app-id>.amplifyapp.com` URL when the build finishes.

Every push to the connected branch redeploys automatically.

## Custom 404 page

App settings > Rewrites and redirects > Add rule:

- Source address: `/<*>`
- Target address: `/404.html`
- Type: `404 (Rewrite)`
