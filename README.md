# Fix A Craving (FAC)

A complete static website using HTML, CSS and vanilla JavaScript. No package installation, build step, backend, API keys or environment variables are required.

## Deploy from GitHub to Vercel

1. Extract this ZIP.
2. Create a GitHub repository and upload **the contents of `fac-vercel/`** to its root. The repository root should contain `vercel.json`, `README.md`, `.gitignore` and `public/`. Upload the extracted files, not the ZIP.
3. In Vercel, choose **Add New → Project**, connect GitHub and import that repository.
4. Use these settings:

| Setting | Value |
| --- | --- |
| Root Directory | Repository root (`.`) |
| Framework Preset | Other |
| Build Command | Empty (no build) |
| Output Directory | `public` |
| Install Command | No installation required |
| Environment Variables | None |

The included `vercel.json` defines the framework, empty build command and output directory. If you keep `fac-vercel/` as a folder inside an existing repository, select that folder as Vercel's Root Directory instead.

5. Click **Deploy**. Subsequent pushes to the linked production branch can redeploy the site through Vercel's Git integration.

`public/index.html` is the entry point and is served at `/`. No SPA rewrites are needed; the site uses section anchors on one page.

## Project files

- `public/index.html` — page markup and external ordering links
- `public/style.css` — responsive styles, colour variables and motion preferences
- `public/script.js` — editable product data, craving selector and heart interactions
- `public/assets/` — all referenced bottle images, brand artwork, photos and video
- `vercel.json` — Vercel deployment configuration
- `.gitignore` — excludes local settings and temporary files

## Run locally

From the project root, with Python 3 installed:

```sh
python3 -m http.server 8000 --directory public
```

Open http://localhost:8000/. You can also open `public/index.html` directly for a basic preview.

## Edit the site

- Update drink names, descriptions, prices, image filenames and categories in the `products` array at the start of `public/script.js`.
- Add new photos to `public/assets/`; use exact, case-sensitive filenames in the product data or HTML.
- Edit page copy and order links in `public/index.html`. The generated product ordering link is in `public/script.js`.
- Change colours in the `:root` variables in `public/style.css`.
- Replace the Craveback artwork or edit its availability copy in `public/index.html`.

All local resources use document-relative paths. Instagram and Grab links are intentionally absolute HTTPS links and open in a new tab. Typography uses Google Fonts over HTTPS with local fallback fonts, so loading those fonts needs internet access. All drink imagery and the video are included locally.

## Customer interactions

Customers can select a craving mood, toggle a drink heart, play the video and follow the order links. Hearts are temporary feedback, not a shopping cart or saved order. Instagram opens FAC's profile, where customers can message the brand. Pickup timing and collection details are confirmed via Instagram. Orders and payment are completed on GrabFood or arranged with FAC, not inside this static website.

## Checks performed on the export

- JavaScript syntax and craving/heart interactions checked.
- HTML, CSS and JavaScript asset references checked with exact filename casing.
- Internal section links checked against IDs.
- Local entry point, CSS, JavaScript, images and video served successfully over HTTP.
- ZIP integrity checked; unused assets, duplicate product data, original hosting metadata, Git history and temporary files excluded.

The archive is ready to import; a GitHub repository or Vercel deployment has not been created by this export. External platform availability and a live Vercel deployment have not been tested.

## Vercel documentation

- https://vercel.com/docs/builds/configure-a-build
- https://vercel.com/docs/project-configuration/vercel-json
