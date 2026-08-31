# 8. DevOps, CI/CD & Deployment Pipeline

The platform is maintained under continuous integration and deployment using GitHub Actions. Any commit merged into the `main` branch triggers automated linting, artifact packaging, and deployment to GitHub Pages.

```yaml
# .github/workflows/deploy-pages.yml
name: Deploy GitHub Pages site

on:
  push:
    branches:
      - main

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Source Code
        uses: actions/checkout@v4

      - name: Setup GitHub Pages Engine
        uses: actions/configure-pages@v4

      - name: Upload Static Web Artifacts
        uses: actions/upload-pages-artifact@v3
        with:
          path: '.'

      - name: Deploy to Global CDN
        id: deployment
        uses: actions/deploy-pages@v4
```
