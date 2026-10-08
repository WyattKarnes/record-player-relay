# record-player-relay

The Spotify login relay page for [NfcRecordPlayer](https://github.com/WyattKarnes/NfcRecordPlayer), published with GitHub Pages at:

https://wyattkarnes.github.io/record-player-relay/callback.html

Spotify only redirects to `https://` addresses (or loopback), so after login it sends the phone here. `callback.html` reads the record player's home-network address out of the `state` parameter and forwards the login code to it. It stores nothing; the code is useless without the PKCE secret, which never leaves the player.

See `docs/setup-spec.md` in the main repo, section *Spotify sign-in*.

## Publishing

1. Create a **public** repo named `record-player-relay` on GitHub. (Pages needs a public repo on this account. That's fine: nothing here is secret.)
2. Push this folder to it.
3. Settings → Pages → Source: *Deploy from a branch*, branch `main`, folder `/ (root)`.
4. In the Spotify Developer Dashboard, add the URL above to the app's Redirect URIs.
