# AI Policy Tracker Tracker — brand assets

## 1. Animated radar (header / hero)

Two ways to use it:

### A. Drop-in iframe (easiest)

    &lt;iframe src="radar-animated.html"
            width="200" height="200"
            style="border:0; background:transparent"
            scrolling="no"&gt;&lt;/iframe&gt;

The radar inside the file is 200×200 by default. To scale, just resize the
iframe — the inner radar is sized via inline style; either edit
`radar-animated.html` (change the outer `.radar-tt` width/height) or wrap
the iframe in a div and set `transform: scale()`.

### B. Inline (no iframe)

Open `radar-animated.html`, copy:

  - the CSS between the `COPY-PASTE EMBED START` / `END` markers
  - the `<div class="radar-tt">…</div>` markup at the bottom of `<body>`

Paste both into your site. The animation is pure CSS — no JS required.

The animation uses `conic-gradient` and `@keyframes`; supported in all
current browsers. Disable globally with `prefers-reduced-motion` if needed:

    @media (prefers-reduced-motion: reduce) {
      .radar-tt .rtt-sweep { animation: none; }
    }

## 2. Favicon set

Sizes generated:

  - favicon-16.png        — browser tabs (small)
  - favicon-32.png        — browser tabs (standard)
  - favicon-48.png        — Windows desktop shortcuts
  - apple-touch-icon.png  — 180×180, iOS home screen
  - icon-192.png          — Android / PWA
  - icon-512.png          — PWA splash, app stores

### Install

In your `<head>`:

    <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32.png">
    <link rel="icon" type="image/png" sizes="16x16" href="/favicon-16.png">
    <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
    <link rel="manifest" href="/site.webmanifest">

`site.webmanifest`:

    {
      "icons": [
        { "src": "/icon-192.png", "sizes": "192x192", "type": "image/png" },
        { "src": "/icon-512.png", "sizes": "512x512", "type": "image/png" }
      ]
    }

### Heads-up on small sizes

The detailed radar (4 mini radars) is dense — at 16/32px it reads as a
fuzzy disc rather than a recognizable mark. If sharpness at small sizes
matters, use the **nested variant** (single mini radar inside a big one)
for `favicon-16.png` / `favicon-32.png` and keep the detailed version for
`apple-touch-icon` / `icon-192` / `icon-512`. Let me know if you want me
to regenerate the small sizes with the nested variant.
