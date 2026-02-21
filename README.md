# 🎭 Uno-Reverse Feed Filters for Instagram & Bluesky

A pair of *ruthlessly judgmental* userscripts that intercept social media feeds and delete content from accounts that are clearly not here for personal vibes (we see you *marketofficial.io policegirl69*). Designed for posting to GitHub so others can benefit from your displeasure with AI spam, brand funnels, and general nonsense.

These work by injecting into the browser and filtering *before* the social apps ever get a chance to show you garbage. If you don’t understand what XHR/fetch interception is, don’t touch this — the code bites if you poke it with a stick.

## 📦 What You’re Getting

### 🧨 Instagram Uno-Reverse Filter

Intercepts Instagram’s network responses and strips out posts from:

* commercial handles (.com / .io / shop / market / etc.)
* “official” accounts (except `zoeykl_official`, of course)
* AI-generated police/law enforcement thirst traps

… before the page UI ever sees them.

### 🔫 Bluesky Uno-Reverse Filter

Does the same for Bluesky XRPC feed JSON — surgically removing posts based on similar handle and post text heuristics.

Both scripts are elegantly hostile towards spam and proud of it.

---

## 📌 Installation (for Mere Mortals)

You need **Tampermonkey**, the world’s most popular userscript manager, before these scripts can do their thing. It’s available for all major browsers (Chrome, Firefox, Edge, Opera, Safari), and it lets you run custom JavaScript on webpages. ([Tampermonkey][1])

Follow the steps for your preferred browser:

### 🧠 1. Install Tampermonkey

**Chrome**

1. Go to the Chrome Web Store.
2. Search for *Tampermonkey* or install directly from the store page.
3. Click **Add to Chrome → Add Extension**. ([Chrome Web Store][2])

**Firefox**

1. Open Firefox Add-ons.
2. Search for *Tampermonkey*.
3. Click **Add to Firefox → Install**. ([Mozilla Add-ons][3])

**Microsoft Edge**

1. Visit the Extensions panel in Edge.
2. Search for *Tampermonkey*.
3. Click **Get → Add Extension**. (Yes, it works in Edge too.) ([Tampermonkey][1])

**Opera**

1. Open the Opera add-ons store.
2. Install the *Tampermonkey Beta* extension.
3. Enable it in your toolbar. ([Opera add-ons][4])

**Safari**

1. On macOS, install Tampermonkey from its official site or extension gallery.
2. If your Safari version is recent, extension support might be limited — check Apple’s documentation. ([GitHub][5])

---

## ✨ Installing the Script

1. After Tampermonkey is installed, click its icon in your browser toolbar.
2. Select **Dashboard → Utilities → Import from URL**.
3. Paste the raw URL of this script from GitHub.
4. Click **Install**.
5. Refresh the social site tab and enjoy the garbage disappearing.

> Tampermonkey will show you warnings about permissions — that’s expected. You’re only allowing it to run these scripts.

---

## 🛠️ How It Works

We intercept network calls (like `fetch` and XHR) **before** Instagram or Bluesky gets the data. Then we:

* look at usernames or post content
* match them against patterns like `market`, `.io`, `official`, `police`, etc.
* remove anything that “looks like spam” so you never see it

If you don’t know how this works — that’s fine — don’t fiddle with the code. If you do know how it works… good. You’re the danger.

---

## ⚠️ Who Should *Not* Modify This

* People who “just wanted to tweak one line”
* People who think regex is a Pokémon
* People who think `= != =` is valid JavaScript
* Everyone except the author and reluctantly… you
