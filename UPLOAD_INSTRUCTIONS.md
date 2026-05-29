# Public Reference Asset Upload Instructions

Upload the CONTENTS of this folder to a public static file host.
For GitHub, use GitHub Pages if you want the simplest reliable public URLs.

## Easiest GitHub Pages Setup

1. Create a new public GitHub repository, for example `youtube-king-reference-assets`.
2. Upload everything inside this `public_reference_assets` folder to the repo root.
3. In GitHub, open `Settings` > `Pages`.
4. Choose `Deploy from a branch`, select `main` and `/ root`, then save.
5. Copy the GitHub Pages URL. It should look like:

```text
https://YOUR_GITHUB_USERNAME.github.io/youtube-king-reference-assets
```

After upload, set this in `.env`:

```env
AI_VIDEO_PUBLIC_ASSET_BASE_URL=https://YOUR_GITHUB_USERNAME.github.io/youtube-king-reference-assets
```

Then check the public URLs:

```powershell
python -m youtube_king.cli check-public-reference-assets --run-id pilot_20260523_201556
python -m youtube_king.cli test-provider-references --run-id pilot_20260523_201556 --provider runway
```

Do not run provider benchmarking until `check-public-reference-assets` validates successfully.

## Raw GitHub Alternative

If you do not want GitHub Pages, raw GitHub can work. Upload the files to the repo root and set:

```env
AI_VIDEO_PUBLIC_ASSET_BASE_URL=https://raw.githubusercontent.com/YOUR_GITHUB_USERNAME/youtube-king-reference-assets/main
```

GitHub Pages is preferred because the URLs are cleaner and easier to inspect.

## Other Good Options

- Cloudflare R2 public bucket
- AWS S3 public bucket
- Netlify/Vercel static folder
- Any HTTPS host that serves raw PNG/JSON files without login

Current configured base URL: `<blank>`
