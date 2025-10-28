# Interactive Birthday Card

Interactive multi-stage birthday card. Runs in the browser. No backend.

## Features

* Welcome screen and sparkles.
* Memory gallery with image upload + captions.
* Cake with 5 hover-to-blow candles and confetti.
* Typewriter letter.
* Wish wall with pinned notes and floating emojis.
* Certificate generator to PNG.
* Secret “Do Not Click” modal.

## Demo

Open `index.html` in any modern browser.

## Quick start

```bash
# clone
git clone <your-repo-url>
cd <repo>

# run locally
# option 1: open index.html directly
# option 2: lightweight server
python3 -m http.server 8000
# visit http://localhost:8000
```

## Deploy (GitHub Pages)

1. Push to `main`.
2. Settings → Pages → Source: **Deploy from a branch**, select `main` and `/root`.
3. Wait for the Pages URL to build.

## File structure

```
.
├── index.html   # markup + JS
└── style.css    # theme and component styles
```

## Customize

* **Title and texts:** edit headings and copy in `index.html`.
* **Letter text:** update `text` inside the `startLetter()` section.
* **Wish wall placeholder:** change the input `placeholder` in the wish stage.
* **Certificate:**

  * The canvas is `#cert-canvas` (1100×800).
  * Edit the second `drawCertificate(name)` function for colors, fonts, and wording.
  * Replace `{age}` strings with a computed value if needed.
  * Replace `name` source as desired (form input, prompt, or hardcoded).
* **Secret modal:** change content inside `#secret-content`.
* **Theme:** tweak CSS variables in `:root` in `style.css`.

## Keyboard and input

* `Enter` or `Space`: advance stage.
* Typing in inputs does not trigger stage changes.
* `Esc`: closes the secret modal.

## Browser support

Modern Chromium, Firefox, and Safari. Uses `IntersectionObserver`, `backdrop-filter` (graceful), and `FileReader`.

## Known quirks

* Directly opening `index.html` blocks image loading via drag-drop on some browsers. Use a local server if needed.
* `{age}` and `{user_name}` placeholders are static. Add your own logic if you want them dynamic.

## Security notes

* Image uploads are local only via `FileReader`. Nothing is sent to a server.
* Basic HTML escaping is applied for wish text.

## License

MIT. Use, modify, and distribute with attribution.

## Credits

Design and code: you. Icons/emoji: system fonts.
