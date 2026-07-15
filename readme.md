# 📻 Get in, we are going to drag joy! — station website

A community radio website for The Joydragger with a private, on-site editor for
live links and journal notes. Netlify Identity protects editing, and Netlify
Database keeps changes available across deploys.

## 🚀 Deploy to Netlify (2 minutes)

1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag this whole folder onto the page
3. Done — Netlify gives you a live URL (you can rename it in Site settings,
   e.g. `dragjoy.netlify.app`, or connect a custom domain later)

Connect the project to a Git repository so Netlify can install the dependencies,
apply the database migration, and deploy the editing functions.

## ✏️ Use the site editor

1. In Netlify, open **Project configuration → Identity** and invite the station owner.
2. Give that user the `editor` or `admin` role.
3. Open the live website and choose **Site editor** in the footer.
4. Sign in with the invited account.

The **Live broadcast** card accepts any secure `https://` live link. YouTube,
Mixlr, Radio.co, and player/embed links appear inside the page when possible;
other live links appear as a button. Clear the field and save to switch off air.

The **Journal note** card creates, edits, and deletes notes directly on the live
site. Date, title, and note text are required; a YouTube link is optional.

## Manual content editing

Archive episodes, support details, and social links still live near the top of
the `<script>` in `index.html`.

Open `index.html` and scroll to the `EDIT ME` banner. Four things:

### Adding an episode
Add a line to the **top** of `EPISODES`:
```js
{ date: "20 Jul 2026", title: "Get in, we are going to drag joy!",
  tags: ["Afrobeats","Soul"],
  mixcloud: "https://www.mixcloud.com/yourname/your-show/",
  cover: "https://link-to-your-show-artwork.jpg" },
```
Paste the normal Mixcloud show URL — clicking the card opens the player in
the bottom dock. Leave `mixcloud: ""` until the upload is ready.
`cover` is your show artwork image; leave it `""` and the site draws a
colorful record-sleeve cover automatically.

### Support links & socials
Set `coffeeUrl` (Buy Me a Coffee, Ko-fi, Paystack or Flutterwave payment link
all work) and `recordsEmail`, and edit the `socials` list.

## 🌱 Ideas for later
- Connect the repo to GitHub + Netlify for push-to-deploy
- A proper 24/7 stream via Radio.co / Azuracast when the community grows
- Custom domain, e.g. dragjoy.live

Dragged with joy. 💛
