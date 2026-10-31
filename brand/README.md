# Sasonica brand assets

The mark: a listener in profile wearing a headset, and a forward chevron that
springs from the mic. Tagline: "Talk to your agents." Chosen 2026-09-22 with
two rings of voice between the mic and the arrow (design history:
https://claude.ai/artifact/Hb3LsHqjB7cEK1dvwPpCRm); the rings came off on
24 Sep; refined 31 Oct 2026: the ear cup inside the head with a band over the
crown, both edged in a darker green, and the chevron's lower arm straight in
towards the head. The masters are kept in step with sasonica-app's `brand/`,
which is where the chat app's icons are made now.

| Token | Hex | Use |
| --- | --- | --- |
| Ground | `#0D1412` | app background |
| Tile | `#15201C` | icon tile, cards, adaptive icon background |
| Signal | `#7FD1AE` | head, mic bead, chevron, accent |
| Signal 62% | `#578E77` | ear cup, band, boom |
| Edge | `#2E5A48` | the line round the cup and band |
| Text | `#E7EFE9` | text on dark |

Type: Fraunces (wordmark, display) + IBM Plex Sans (body).

Files:
- `sasonica-mark.svg` — the master: the mark on its rounded tile.
- `android/` — `mipmap-*/ic_launcher.png` (legacy), `mipmap-*/ic_launcher_foreground.png` +
  `ic_launcher_foreground.svg` + `ic_launcher_background.xml` (adaptive icon, mark inside the
  66 dp safe zone), `drawable-*/ic_notification.png` + `.svg` (one colour, alpha only: head
  and chevron — the cup, band and boom are too fine at 24 dp), `playstore-512.png`.
- `web/` — `favicon.svg`, `favicon-32.png`, `apple-touch-icon.png`, `icon-192.png`, `icon-512.png`.

Regenerate every derived size with `python3 brand/regen.py` (needs cairosvg); they are derived,
never hand-edited. It also writes both apps' own icons — Sasonica (`android/`) and Sasonica
Next (`chat/android/`) — so `brand/` and the apps cannot drift. Sasonica's debug variant keeps
its own icons on purpose: they are how you tell a debug install from the release one.

The two apps sit side by side on the home screen, so Sasonica — the Audiobookshelf fork —
carries an `ABS` wordmark under the mark, and Next carries the mark alone. The letters are
drawn from the mark's own vocabulary (monoline, round caps) rather than set in a typeface, so
regenerating needs no font installed. The wordmark goes in the adaptive foreground as well as
the legacy icon: a launcher on Android 8 or later never shows the legacy one.
