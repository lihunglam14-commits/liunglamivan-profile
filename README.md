# Ivan Li Personal Academic Website

Static personal profile / paper website for GitHub Pages. The site is a plain HTML page with inline CSS and JavaScript plus local image assets. No build step is required.

## Final structure

```text
.
├── .github/
│   └── workflows/
│       └── deploy-pages.yml
├── assets/
│   ├── cambodia.png
│   ├── carpediem.jpg
│   ├── dodo_voicebox.png
│   ├── hungary.png
│   ├── italy.png
│   ├── ivan_profile.png
│   ├── japan_kyoto.png
│   ├── logo_carpediem.png
│   ├── logo_dodo.png
│   ├── logo_dodofly.png
│   └── logo_juice.png
├── backup/
│   └── original-export.zip
├── .gitignore
├── .nojekyll
├── README.md
└── index.html
```

`backup/` is only a local archive copy. It is ignored by Git and should not be uploaded if you use GitHub's web upload interface.

## GitHub Pages launch steps

### Recommended: Deploy from a branch

1. Create a GitHub repository.
2. Put `index.html`, `assets/`, `.nojekyll`, and this `README.md` in the repository root.
3. Push the repository to the `main` branch.
4. On GitHub, open `Settings` -> `Pages`.
5. Under `Build and deployment`, set `Source` to `Deploy from a branch`.
6. Set `Branch` to `main` and `Folder` to `/ (root)`.
7. Click `Save`.
8. Wait for GitHub Pages to finish publishing.

Expected URL:

- Project site: `https://<your-github-username>.github.io/<repo-name>/`
- User site (only if the repo name is exactly `<your-github-username>.github.io`): `https://<your-github-username>.github.io/`

### Optional: GitHub Actions deployment

This repo also includes `.github/workflows/deploy-pages.yml`.

1. Push the repository to `main`.
2. On GitHub, open `Settings` -> `Pages`.
3. Under `Build and deployment`, set `Source` to `GitHub Actions`.
4. GitHub will run the included workflow automatically on each push to `main`.

## Notes

- The site is plain static HTML, not a framework app.
- All local site paths are relative, so the page works as a project site under `/repo-name/`.
- CSS and JavaScript are embedded directly in `index.html`.
- `.nojekyll` is included so GitHub Pages serves the site without Jekyll processing.
