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
└── README.md
```

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
