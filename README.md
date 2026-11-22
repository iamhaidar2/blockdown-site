# Blockdown marketing site

The promotional website for [Blockdown](https://github.com/iamhaidar2/blockdown-app).
Hostinger serves `public/` as plain files; the small, zero-dependency Node.js static
server is only for previewing it locally.

```sh
npm start            # http://localhost:4321
# or: PORT=8080 npm start
```

No `npm install` needed. It uses only Node's built-in `http`/`fs` modules.

## Files

```
.
  server.js          tiny static server for local preview (path-traversal-safe, correct MIME types)
  package.json       start script + engines (node >= 18)
  public/
    .htaccess        Hostinger rules: 404 page, download types, headers, cache times
    index.html       the landing page
    404.html         the "not found" page
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

blockdown.io is a Hostinger web app connected to this repo with **Framework: Other**,
**Build command: None**, **Output directory: `public`** and an empty **Entry file**.
Every push to `main` publishes `public/` about 15 seconds later. No Node process runs
on the server: the hosting plan's process limit is shared by every site on it, and a
running Node app uses about 11 of its 120.

`public/.htaccess` does on Hostinger what `server.js` does locally: `404.html` for
unknown paths, the installers sent as plain downloads, `nosniff`, and cache times
(pages and CSS are re-checked on every visit, so a push shows up straight away).
