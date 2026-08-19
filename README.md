# Personal site — Yizhou Wu

Single self-contained `index.html`. No build step, no dependencies, no framework.
Edit the HTML directly; refresh the browser.

## Preview locally
    cd ~/personal-site && python3 -m http.server 8000
Then open http://localhost:8000

## Deploy to GitHub Pages
1. Create a **public** repo named exactly `mclwu22.github.io`
   (use your real GitHub username if it isn't `mclwu22`).
2. From this folder:

       git init -b main
       git add .
       git commit -m "personal site"
       git remote add origin git@github.com:mclwu22/mclwu22.github.io.git
       git push -u origin main

3. Repo → Settings → Pages → Source: `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Live in ~1 minute at https://mclwu22.github.io

To update: edit, `git commit -am "..."`, `git push`. Pages redeploys automatically.

See `TODO.md` for what still needs filling in.
