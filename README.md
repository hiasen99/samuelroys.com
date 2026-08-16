# samuelroys.com

Personal landing page. One static `index.html` — no build step, no dependencies.

## Editing

Open `index.html` in any editor. The file is commented into sections:

| Section | What to change |
|---|---|
| `HEADER` | Name, tagline, bio, contact chips |
| `PROJECTS` | Copy an `<a class="card">` block to add a project |
| `WRITING` | Delete the `<p class="empty">` line, uncomment the `<ul class="posts">` block |
| `EXPERIENCE` | Replace the placeholder `<li>` entries |
| `CONTACT` | Email address |

Colors live in the `:root` block at the top of the `<style>` tag. Dark mode is
handled automatically by the `prefers-color-scheme` block right below it — change
`--accent` in both places to reskin the whole site.

## Previewing locally

```sh
cd "path/to/this/folder"
python3 -m http.server 8000
# open http://localhost:8000
```

Or just double-click `index.html`.

## Deploying

Connected to Netlify. Every push to `main` redeploys automatically:

```sh
git add -A
git commit -m "Update site"
git push
```

No build command — Netlify publishes the folder root as configured in `netlify.toml`.

### First-time setup

1. Create an empty repo on GitHub (no README, no .gitignore).
2. ```sh
   git remote add origin git@github.com:USERNAME/REPO.git
   git branch -M main
   git push -u origin main
   ```
3. In Netlify: **Add new site → Import an existing project → GitHub**, pick the repo.
   Leave build command empty, publish directory `.`.
4. **Domain settings → Add custom domain → `samuelroys.com`**, then point the DNS at
   Netlify (same place you set up the `timing.` and `handwriting.` subdomains).
