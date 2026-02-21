# Instagram Uno Reverse Filter

Because the modern feed is a landfill and I got tired of manually blocking AI-generated police thirst traps, dropshipping empires, crypto prophets, and “_official” accounts that were born yesterday.

This userscript intercepts Instagram’s network responses and removes unwanted accounts **before the UI ever sees them**. They simply never existed. ✨

## 📦 How to Install

### 🧠 What You’re Installing

Tampermonkey is a userscript manager extension that lets your browser run custom scripts like this one. You’ll need it before you can use the block-filter script below. ([Tampermonkey][1])

---

### 🔵 Google Chrome

1. Open Chrome.
2. Visit the **Tampermonkey extension page** on the Chrome Web Store. ([Chrome Web Store][2])
3. Click **“Add to Chrome”** and confirm.
4. Once installed, a Tampermonkey icon will appear to the right of the address bar.
5. Click that icon, open **Dashboard**, then **Add new script**.
6. Paste your userscript code into the editor and save.

---

### 🌀 Opera

1. Open Opera.
2. Search for **Tampermonkey in the Opera Add-ons store** (or go via Tampermonkey.net). ([Opera add-ons][3])
3. Click **“Add to Opera”** and confirm installation.
4. After installation, the Tampermonkey icon will appear near the address bar.
5. Open the Dashboard, add a new script, and paste your code.

> *Note:* On some versions of Opera, installing the “Chrome Extensions” add-on first can make installing Chrome extensions (including Tampermonkey) easier. ([openuserjs.org][4])

---

### 🦊 Mozilla Firefox

1. Open Firefox.
2. Go to the **Tampermonkey add-on page for Firefox** and click **“Add to Firefox”**. ([Mozilla Add-ons][5])
3. Approve the extension permissions.
4. See the Tampermonkey icon appear in your toolbar.
5. Click it, choose **Dashboard**, then **Add new script**.
6. Paste your userscript code and save.

---

### 🧠 After Installation

Once Tampermonkey is installed and your script is saved:

* Ensure the script is **enabled** in the Tampermonkey dashboard.
* Visit Instagram in the same browser — the script will begin working automatically.
* You can return to the dashboard to **edit, disable, or remove** the script any time.

[1]: https://www.tampermonkey.net/?utm_source=chatgpt.com "Tampermonkey: Home"
[2]: https://chromewebstore.google.com/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en&utm_source=chatgpt.com "Tampermonkey - Chrome Web Store"
[3]: https://addons.opera.com/en/extensions/details/tampermonkey-beta/?utm_source=chatgpt.com "Tampermonkey extension - Opera add-ons"
[4]: https://openuserjs.org/about/Tampermonkey-for-Opera?utm_source=chatgpt.com "About / Tampermonkey for Opera"
[5]: https://addons.mozilla.org/en-US/firefox/addon/tampermonkey/?utm_source=chatgpt.com "Tampermonkey – Get this Extension for Firefox (en-US)"


---

## What This Does

* Hooks `window.fetch`
* Hooks `XMLHttpRequest`
* Intercepts Instagram JSON responses
* Recursively walks the data tree
* Deletes any object owned by a username matching configured patterns
* Returns a surgically altered response back to Instagram

Instagram sends you content.
The script looks at it.
The script decides it’s garbage.
Instagram never gets it back.

Uno reverse.

---

## What This Is Not

* It is not a packet firewall.
* It does not “reject packets” at the TCP layer.
* It does not send angry data back to Meta HQ.
* It does not violate your login session.
* It does not magically change the algorithm.

It simply edits the response in your browser before Instagram consumes it.

If you do not understand how monkeypatching `fetch()` works, do not modify this script.

If you do not understand recursive JSON mutation, do not modify this script.

If your first instinct is to “clean up unused parts,” resist that instinct.

---

## Why It Exists

Because:

* Every third account is `_official`
* Everyone has a `.io`
* Every cop thirst trap is AI-generated
* Dropshipping never dies
* Crypto refuses to remain buried

And I value my sanity.

---

## What It Filters By Default

The script aggressively targets usernames containing:

* `official`
* `.com`
* `.io`
* `market`, `shop`, `store`, `promo`, `brand`
* `crypto`, `forex`, `bet`, `casino`
* Corporate suffixes like `LLC`, `Inc`
* Police/law enforcement bait keywords (`police`, `cop`, `sheriff`, `trooper`, etc.)

It excludes `your_username_here`.

Yes, intentionally. No, don’t remove it unless you enjoy self-inflicted chaos.

---

## Stability Notes

Instagram changes its internal API structure regularly.

If:

* Your feed stops loading
* Things appear blank
* Infinite scroll gets weird

Turn on `DEBUG = true` in the script and observe what’s being removed.

This script is aggressive by design. You can dial it back. I won’t.

---

## Disclaimer

This script modifies client-side responses only. It just refuses to display nonsense.
