# Blockdown marketing site

The promotional website for [Blockdown](https://github.com/iamhaidar2/blockdown-app),
served by a small, zero-dependency Node.js static server.

```sh
npm start            # http://localhost:4321
# or: PORT=8080 npm start
```

No `npm install` needed. It uses only Node's built-in `http`/`fs` modules.

## Files

```
.
  server.js          tiny static server (path-traversal-safe, correct MIME types)
  package.json       start script + engines (node >= 18)
  public/
    index.html       the landing page
    styles.css       Slate + Indigo theme
    logo.svg         Blockdown mark: a "B" next to a blinking down arrow
    downloads/       the Windows installer the Download button points to
```

## The logo

`public/logo.svg` is the Blockdown mark: a rounded indigo tile with a white frame,
a "B", and a down arrow, echoing the classic Markdown "M" mark. The arrow blinks
with a self-contained CSS animation (it respects `prefers-reduced-motion`), so it
animates even when the file is used as an `<img>` or favicon.

## Deploy

It is static files plus a static server, so most hosts work:

- Static hosts (GitHub Pages, Netlify, Vercel, Cloudflare Pages, Hostinger): serve the `public/` folder.
- Node hosts (Render, Railway, Fly): run `npm start`; it honors `PORT`.
