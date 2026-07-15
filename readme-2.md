# 📻 Get in, we are going to drag joy! — station website

The home of The Joydragger's community radio show: live broadcasts, the full
show archive, a journal, and a support corner. One self-contained `index.html`,
hosted free on **GitHub Pages** at **[joydraggerradio.rocks](https://joydraggerradio.rocks)**.

No build tools, no backend, no databases — nothing that can meter, bill, or
pause the station.

## ✏️ How to edit the site (the whole workflow)

1. Open `index.html` in this repo and click the **pencil icon**
2. Scroll to the `EDIT ME` banner near the top of the `<script>`
3. Make your change (see recipes below)
4. **Commit changes** — the live site updates itself in about a minute

Two rules prevent 99% of breakage: every entry ends with a comma, and text
stays inside its double quotes. If the page ever goes blank after an edit,
open the file's **History**, view the last good version, and restore it —
nothing is ever lost.

### Going live

Paste your live link into `liveEmbedUrl` and commit:

```js
liveEmbedUrl: "https://www.youtube.com/live/XXXXXXXX",
```

The badge flips to **ON AIR** and the player appears in the Live section.
YouTube, Mixlr, Radio.co and embed/player links render inside the page; any
other `https://` link shows as an "Open the live broadcast" button. Set it
back to `""` after the show to go off air.

### Adding an episode

Add a line to the **top** of `EPISODES`:

```js
{ date: "20 Jul 2026", title: "Get in, we are going to drag joy!",
  tags: ["Afrobeats","Soul"],
  mixcloud: "https://www.mixcloud.com/joydragger/your-show/",
  cover: "https://link-to-your-show-artwork.jpg" },
```

Clicking the card opens the player in the bottom dock. Mixcloud links embed
the player; Oroko links show a "Listen on Oroko Radio" button; leave
`mixcloud: ""` until the upload is ready. Leave `cover: ""` and the site
draws a colorful record-sleeve automatically.

### Writing a journal post

Add to the **top** of `POSTS`:

```js
{ date: "20 Jul 2026", title: "Show notes vol. 2",
  body: "Tonight we played...",
  youtube: "https://www.youtube.com/watch?v=VIDEO_ID" },
```

`youtube` is optional — regular watch links, share links and embed links all
work. Line breaks in `body` (written as `\n`) show as line breaks on the site.

### Support links & socials

In `CONFIG`: set `coffeeUrl` (Buy Me a Coffee, Ko-fi, Paystack or Flutterwave
payment link all work), `recordsEmail` for record donations, and edit the
`socials` list.

## 🌍 Hosting notes

- **Host:** GitHub Pages, deployed from the `main` branch of this repo
  (Settings → Pages). Every commit auto-deploys.
- **Domain:** `joydraggerradio.rocks` — the `CNAME` file in this repo tells
  GitHub Pages about it; don't delete that file. The domain registration and
  DNS records live in the Netlify dashboard (registered there until Jun 2027):
  four A records → `185.199.108.153 / .109.153 / .110.153 / .111.153`, and
  `www` → CNAME → `kamnele.github.io`.
- **Audio:** streams from Mixcloud/Oroko, so the site itself uses almost no
  bandwidth no matter how many people tune in.

## 🌱 Ideas for later

- A proper 24/7 stream via Radio.co / AzuraCast when the community grows
- Real cover art on every archive card (`cover` field per episode)
- A newsletter link in `socials` when there's one to share

Dragged with joy. 💛
