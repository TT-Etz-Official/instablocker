# Instagram Uno Reverse Filter

Because the modern feed is a landfill and I got tired of manually blocking AI-generated police thirst traps, dropshipping empires, crypto prophets, and “_official” accounts that were born yesterday.

This userscript intercepts Instagram’s network responses and removes unwanted accounts **before the UI ever sees them**. They simply never existed. ✨

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
