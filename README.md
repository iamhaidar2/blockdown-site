# BlockDown — marketing site

The promotional website for [BlockDown](https://github.com/iamhaidar2/blockdown-app),
served by a small, **zero-dependency** Node.js static server.

```sh
npm start            # → http://localhost:4321
# or: PORT=8080 npm start
```

No `npm install` needed — it uses only Node's built-in `http`/`fs` modules.

## Files

```
.
├─ server.js          tiny static server (path-traversal-safe, correct MIME types)
├─ package.json       start script + engines (node >= 18)
└─ public/
   ├─ index.html      the landing page
   ├─ styles.css      Slate + Indigo theme
   └─ logo.svg        BlockDown mark — "B↓" with a blinking down arrow
```

## The logo

`public/logo.svg` is the BlockDown mark: a rounded indigo tile with a white frame
and a **`B↓`**, mirroring the classic Markdown `M↓` symbol. The down arrow blinks
via a self-contained CSS animation (respects `prefers-reduced-motion`), so it
animates even when used as an `<img>` or favicon.

## Deploy

It's static files + a static server, so anything works:
- **Static hosts** (GitHub Pages, Netlify, Vercel, Cloudflare Pages): point them at `public/`.
- **Node hosts** (Render, Railway, Fly): run `npm start`; it honors `PORT`.
