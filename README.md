# Chompi's Coffee Cup ☕

Your Boston coffee diary — with reviews, a map, bean catalog, and a taste quiz that recommends beans to buy.

---

## 🚀 How to deploy this (non-developer version)

### Step 1: Put the files on GitHub

You already have your site on Netlify, which means you have a GitHub repo. Replace the files in that repo with everything in this folder:

```
index.html
styles.css
app.js
data/cafes.json
data/beans.json
data/quiz.json
admin/index.html
admin/config.yml
README.md
```

**The easiest way** if you're not comfortable with git:

1. Go to your repo on github.com
2. For each file above, click "Add file" → "Upload files" (or edit the existing one)
3. Drag the file in, commit the change
4. Netlify will auto-deploy within 1-2 minutes

**After this step, your site is live** — but the admin panel won't work yet. Do Step 2 next.

---

### Step 2: Turn on Netlify Identity & Git Gateway (for the admin panel)

This is what lets you log in at `yoursite.com/admin` and add cafés through a form instead of editing JSON by hand.

1. Log into [app.netlify.com](https://app.netlify.com) and open your site
2. Go to **Site configuration → Identity** → click **Enable Identity**
3. Under **Registration**, change it to **Invite only** (so randos can't sign up)
4. Scroll to **Services → Git Gateway** → click **Enable Git Gateway**
5. Go to the **Identity** tab (top nav) → click **Invite users** → enter your email
6. Check your email, follow the invite link, set a password

That's it. Now visit `https://chompiscoffeecup.netlify.app/admin/` and log in.

---

### Step 3: Add your first café using the admin

1. Go to `/admin/` and log in
2. Click **Cafés** in the sidebar
3. Click **All Cafés** → you'll see the list of your existing cafés
4. Scroll to the bottom of the list, click **Add Cafés** to add a new one
5. Fill in the form. For lat/lng coordinates: open Google Maps, right-click the café location, click the numbers that appear — that copies them to your clipboard
6. Click **Publish** in the top right. Netlify will redeploy in ~1 minute and your new café will be live!

---

## 📋 Getting lat/lng for the map

For each new café:
1. Go to [maps.google.com](https://maps.google.com)
2. Search for the café
3. Right-click directly on the pin
4. Click the numbers at the top of the context menu (e.g. `42.3509, -71.0780`)
5. First number = latitude, second = longitude
6. Paste them in the admin form

---

## 💰 Making money: the affiliate playbook

Your site has a natural path for affiliate links. For every bean, paste an affiliate URL in the "Buy URL" field. Here's how to sign up:

### Easy wins to set up first

- **Amazon Associates** (`affiliate-program.amazon.com`) — most major roasters sell on Amazon too. Easiest approval, smallest commission (~4%). Good for getting started.
- **Trade Coffee** (`drinktrade.com/affiliates`) — they partner with dozens of specialty roasters. ~$10-15 per subscription signup. Great for a "find your beans" concept like yours.
- **ShareASale** (`shareasale.com`) — marketplace with coffee brands like Atlas Coffee Club, Volcanica, and more.

### Direct roaster programs

Email these roasters directly once you have traffic — they often have affiliate programs but don't advertise them:
- George Howell Coffee (Boston local, they'd love you promoting them)
- Pavement Coffeehouse
- Stumptown (has an affiliate program via Rakuten)
- Blue Bottle (affiliate via Impact.com)
- Verve Coffee

### Pro tip

Write tasting-note-rich reviews. A bag someone buys because your "why this matches you" line said "fig and dark chocolate on a rainy Boston afternoon" beats any search-engine listing. Your content is your moat.

---

## 🗺️ What's under the hood

- **No backend, no database** — pure static site, free forever on Netlify
- **Content lives in `data/*.json`** — Decap CMS edits these via a friendly form
- **Taste matcher is rules-based** — scores beans against quiz answers. Magic without AI.
- **Map uses Leaflet + CARTO tiles** — free, no API key
- **Fonts: Fraunces (display) + Inter Tight (body)** — warm, editorial, café-ish

---

## 🛠️ Ideas for v2 (when you're ready)

- **Email capture** — "Get new café reviews in your inbox" — use Netlify Forms (free)
- **A bean of the month** — featured bean on the homepage
- **Coffee crawls** — curated itineraries ("A perfect Saturday in Back Bay")
- **User reviews** — let visitors rate cafés (needs Netlify Identity for all users)
- **Sell your own beans** — add Stripe checkout when you're ready to become a reseller
- **Instagram embed** — pull in your own café photos
- **SEO pages** — one page per neighborhood ("Best coffee in Back Bay")

---

## 🆘 If something breaks

- **Site not updating?** Go to Netlify → Deploys → check if the latest deploy succeeded. If it failed, click in to see the error.
- **Admin won't load?** Make sure Identity is enabled and you're invited as a user.
- **Map is empty?** Check that each café has `lat` and `lng` filled in.
- **Need to edit a JSON file directly?** You can — just keep the commas and brackets matched, or use jsonlint.com to validate.

Made with ☕ and love.
