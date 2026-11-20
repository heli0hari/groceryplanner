# Grocery Planner

Shared grocery list + weekly shop-day vote. Real-time via Firebase Firestore. No login — anyone with the link can edit.

## Setup (5 min)

1. **Firebase console** → Add project (Analytics off).
2. **Build → Firestore Database** → Create database → Production mode → any region (e.g. `eur3`).
3. **Firestore → Rules** → paste the contents of `firestore.rules` → Publish.
4. **Project settings → Your apps → Web (`</>`)** → register app → copy the `firebaseConfig` object into `config.js`.
5. Push to GitHub, then **repo Settings → Pages → Deploy from branch `main` / root**.
   Site: `https://heli0hari.github.io/groceryplanner/`

Without a config, the page runs in **local demo mode** (data stays in that browser).

## Use

- First visit asks for your name (stored on that device).
- Add items with qty + category; tap any text to edit; tick to move to the basket; "Clear bought" after shopping.
- Tap the days you're free — the best day is starred.
- Separate lists for different groups: add `?g=flat2` to the URL.

## Notes

- The Firebase web config is public by design; the rules limit what can be written. Anyone with the URL can edit or delete — fine for friends, don't post the link publicly.
- Data path: `groups/{group}/items/*` and `groups/{group}/weeks/{monday-date}`.
