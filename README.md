# The Sketchbook

A static, read-only sketch gallery for GitHub Pages. Visitors can browse the
gallery and open sketch details. Admin uploads and visitor reviews are not
available on this version.

## Publish on GitHub Pages

1. Create a **new public** repository on GitHub. Name it `sketchbok-gallery`;
   leave
   the README, `.gitignore`, and license options unchecked.
2. Open PowerShell in this project folder. In File Explorer, open the folder,
   click the address bar, type `powershell`, and press Enter.
3. Run these commands, replacing the URL with the HTTPS URL shown by GitHub:

   ```powershell
   git init
   git add .
   git commit -m "Publish static sketch gallery"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/the-sketchbook.git
   git push -u origin main
   ```

   The `.gitignore` keeps the admin, backend, database, and `.env` files out of
   the repository. The gallery page, its runtime, sketch list, and images are
   included.
4. On GitHub, open the repository's **Settings > Pages**. Under **Build and
   deployment**, set the source to **GitHub Actions**.
5. Open the **Actions** tab and wait for **Publish static gallery** to finish
   successfully. Your public site URL will be
   `https://YOUR-USERNAME.github.io/sketchbok-gallery/`.

To change the public gallery, edit `sketches.json` and add or remove image files
in `uploads/`. Each entry needs an `id`, `title`, `story`, and `image` path such
as `./uploads/my-sketch.jpg`. Commit and push the changes; GitHub Actions will
publish them automatically.

## Local full-stack files

The excluded `server.mjs`, admin files, and `data/` database remain in this
folder for local use, but are not part of the public GitHub Pages deployment.
GitHub Pages is static hosting, so it cannot run uploads, admin management,
or reviews.
