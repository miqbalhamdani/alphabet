# Keyboard Letter Display

A simple single-page web app that displays the last alphabet key you press.

- Large uppercase letter (A-Z)
- Matching lowercase letter (a-z)
- Non-letter keys are ignored

## Preview

When the page loads, it starts with:

- Uppercase: `A`
- Lowercase: `a`

Press any keyboard letter key to update both values.

## Project Structure

```text
.
├── index.html
├── package.json
├── wrangler.toml
└── README.md
```

## Cloudflare Pages (Wrangler Setup)

This project is ready to deploy with Wrangler using:

- [wrangler.toml](wrangler.toml)
- [package.json](package.json)

### 1. Install dependencies

```bash
npm install
```

### 2. Log in to Cloudflare

```bash
npx wrangler login
```

### 3. Create your Pages project (first time only)

Create a Pages project in the Cloudflare dashboard first, then deploy.

### 4. Deploy

Option A: deploy directly (Wrangler can prompt for/select project)

```bash
npm run deploy
```

Option B: deploy to a specific project name

```bash
export CF_PAGES_PROJECT="your-pages-project-name"
npm run deploy:project
```

After deployment, Cloudflare will return the live URL.

## Notes

- This is a static app, so `pages_build_output_dir = "."` is used.
- `compatibility_date` is set in [wrangler.toml](wrangler.toml) and can be updated any time.

## How to Run

1. Open `index.html` directly in your browser.
2. Click on the page (if needed) to ensure it is focused.
3. Press any key from `A` to `Z`.

## How It Works

- The app listens to the `keydown` event on `window`.
- It validates input using the regex `^[a-zA-Z]$`.
- If valid, it updates:
  - The uppercase heading (`#letter`)
  - The lowercase text (`#letterLower`)

## Customization

You can edit CSS variables in `:root` inside `index.html`:

- `--bg`: background base color
- `--fg`: main text color
- `--accent`: highlight color

You can also adjust text size by editing the `font-size` values in `.letter` and `.letter-lower`.

## Browser Support

Works in all modern browsers that support:

- `addEventListener`
- `String.prototype.toUpperCase()`
- `String.prototype.toLowerCase()`
