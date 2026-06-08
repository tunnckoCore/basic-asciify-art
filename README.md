# Ethscription gzip font demo

Small Vite page comparing direct Ethscriptions `/data` font URLs with Calldata `/content` font URLs.

## Endpoint split

`/data` should mean raw canonical bytes: the exact payload stored on-chain. If that payload starts with gzip bytes (`1f 8b 08`), clients should treat it as gzip data and decide whether to decompress it themselves. This is useful for parity, verification, indexing, and archival use.

`/content` should mean browser-usable content: decode stored gzip payloads when needed, serve the real asset bytes with the real `Content-Type`, and allow cross-origin embedding. This is what works for `@font-face`, `<img>`, CSS, JS, HTML, SVG, JSON, WASM, and similar web consumers.

In short: `/data` is what is on-chain; `/content` is what the browser can use.

## Run

```bash
npm install
npm run dev
```
