# Ivan Li Personal Academic Website

Static personal profile / academic website for GitHub Pages. The site is plain HTML with inline CSS and JavaScript plus local image assets. No build step, package manager, or framework is required.

## Deployment Method

Use GitHub Pages from the `main` branch root.

GitHub setting:

```text
Settings -> Pages -> Build and deployment
Source: Deploy from a branch
Branch: main
Folder: / (root)
```

This is the recommended method because the website is already static and can be served directly from the repository root.

The workflow file at `.github/workflows/deploy-pages.yml` is manual-only and is not part of the normal publishing flow. Do not switch Pages to `GitHub Actions` unless you intentionally decide to use that alternate method later.

## Project Structure

```text
.
|-- .github/
|   `-- workflows/
|       `-- deploy-pages.yml
|-- assets/
|   |-- cambodia.png
|   |-- carpediem.jpg
|   |-- dodo_voicebox.png
|   |-- hungary.png
|   |-- italy.png
|   |-- ivan_profile.png
|   |-- japan_kyoto.png
|   |-- logo_carpediem.png
|   |-- logo_dodo.png
|   |-- logo_dodofly.png
|   `-- logo_juice.png
|-- backup/
|   `-- original-export.zip
|-- .gitignore
|-- .nojekyll
|-- README.md
`-- index.html
```

`backup/` is only a local archive copy. It is ignored by Git and should not be uploaded to GitHub.

## First-Time GitHub Upload

Run these commands from the project root:

```bash
git init
git branch -M main
git status -sb
git add index.html assets README.md .nojekyll .github/workflows/deploy-pages.yml .gitignore
git commit -m "Initial personal website"
git remote add origin https://github.com/<your-github-username>/<repo-name>.git
git push -u origin main
```

Then open the repository on GitHub and set Pages to:

```text
Source: Deploy from a branch
Branch: main
Folder: / (root)
```

Expected public URL:

- Project site: `https://<your-github-username>.github.io/<repo-name>/`
- User site: `https://<your-github-username>.github.io/` if the repo is named `<your-github-username>.github.io`

## Normal Update Workflow

After editing `index.html`, `assets/`, or documentation, run:

```bash
git status -sb
git add index.html assets README.md .nojekyll .github/workflows/deploy-pages.yml .gitignore
git commit -m "Update personal website"
git push origin main
```

After the push finishes, GitHub Pages should publish the updated site automatically. Publishing is not instant; wait for the Pages deployment to finish.

If the public site does not update immediately:

- Check the repository's GitHub Pages deployment status.
- Check the repository's Actions tab for any Pages build/deployment messages.
- Refresh the public page with a cache bypass: `Ctrl+F5` on Windows or `Cmd+Shift+R` on macOS.

## Notes

- The site is plain static HTML, not React, Vite, Next.js, or another framework.
- `index.html` is the main website file.
- CSS and JavaScript are embedded directly in `index.html`.
- Assets live in `assets/`.
- `.nojekyll` is included so GitHub Pages serves files directly without Jekyll processing.
- Do not upload `backup/` to GitHub.
