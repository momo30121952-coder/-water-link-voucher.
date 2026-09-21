# Water Link — Guest Voucher Generator

Internal tool for creating and printing guest-facing experience vouchers
for Water Link (Dubai + Abu Dhabi watersports). Single static page —
`index.html` — no build step.

## Data storage

Shared, synced across every staff computer via Firebase Firestore
(project `wl-voucher`). Firestore security rules are in `firestore.rules`
— paste that file's contents into the Firebase console under
Firestore Database → Rules.

If Firebase can't be reached (offline, misconfigured), the app falls back
to saving data in that browser's local storage only, so it never breaks —
it just stops being shared until Firebase is reachable again.

## Deploying

This repo deploys to Vercel with zero configuration — it's a static
`index.html`, nothing to build. Import the repo in Vercel and it just
works.

## Guest-facing rule

Prices, rates, costs and commissions must never appear on the printed
voucher / PDF. This is enforced in the code (voucher rendering never
reads product pricing fields) — do not add pricing fields to the voucher
template.
