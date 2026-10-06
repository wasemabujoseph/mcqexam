# ExamSprint

A static, phone-friendly MCQ practice app. It includes the full dermatology question set, answer keys, and explanations, plus two practice layouts:

- **One question** — answer and check questions individually.
- **Full questions** — scroll through the complete exam, answer in any order, then submit for a score and review.

The app runs in the browser. Your answers and pasted question text are saved in that browser's local storage; there is no account or server backend.

## Publish with GitHub Pages

1. Create a GitHub repository and upload or push the contents of this folder to its root. `index.html` must be at the repository root.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **GitHub Actions** as the source.
4. Commit this repository's included workflow. GitHub will build and publish the site automatically.
5. Open **Settings → Pages** to find the published URL. It will look like `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`.
6. Open that URL on your phone. Use your browser's **Add to Home Screen** or **Install app** option to keep it like an app.

The first visit needs an internet connection. After the page has loaded once, the service worker caches the app so it can reopen offline. A new deployment updates the cached files on the next visit.

## Run locally

Open `index.html` in a browser. The quiz works locally; install/offline caching is enabled when served over HTTPS, such as GitHub Pages, or from localhost.

## Included files

- `index.html` — app and embedded 160-question dermatology practice set
- `manifest.webmanifest` — installable app metadata
- `sw.js` — offline app cache
- `assets/icon.svg` and PNG sizes — app icons for browsers and phone installation
- `.github/workflows/deploy.yml` — GitHub Pages deployment workflow

## Updating the exam

You can paste a different exam into the app's setup box. To change the built-in default question set, edit the `SAMPLE` text in `index.html`, then commit and push the change.
