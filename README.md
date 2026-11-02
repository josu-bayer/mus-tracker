# Mus Tracker

A shared tracker for Mus (a Basque card game) tournaments. Log each tournament, see statistics and breakdowns, and sync live across devices. Installable web app on Firebase.

## Contents

- [Features](#features)
- [How it is built](#how-it-is-built)
- [Sample data](#sample-data)
- [Running your own copy](#running-your-own-copy)
- [Security](#security)

## Features

- One entry per tournament with date, entry fee, number of pairs, round reached, final position and prize.
- Statistics and breakdowns, with a hand-drawn line chart on a canvas.
- Live sync between devices, offline use, and a connection indicator that shows online, offline or syncing.
- A manual refresh button, because installed phone apps can resume without refetching.

## How it is built

- A single `index.html` with one module script. No framework, no build step.
- Firebase Cloud Firestore with a persistent local cache, and Hosting.
- A network-first service worker, a web manifest and icons.
- Collections: `torneos` for tournaments and `meta` for migration and seed markers.

## Sample data

The `SEED` list in `index.html` holds sample tournaments. Venues and notes are placeholders. Replace the list with your own history, or empty it.

## Running your own copy

1. Create a Firebase project and enable Cloud Firestore.
2. Replace the `YOUR_...` values in the `firebaseConfig` object in `index.html`.
3. Run `firebase use --add`, then `firebase deploy`.

## Security

`firestore.rules` is not part of this repository. The original deployment used open rules for two trusted users, which is not suitable for a public address. Write owner-only rules and add sign-in before storing real data.

## Licence

MIT. See [LICENSE](LICENSE).
