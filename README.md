# 🌀 FLING ARENA

A **10-player battle royale fling battler** for the browser — inspired by the Roblox octagon fling game from [this Instagram reel](https://www.instagram.com/reel/Dd6ipTWORBU/).

**🎮 Play it live:** https://super-starship-01.netlify.app/

## How it works

- Up to **10 players** fling each other around an octagonal arena at the same time.
- Get knocked out of the ring and you're eliminated. Last one standing wins the round.
- The arena **shrinks** mid-round (starts at 15s, down to 45% over 20s).
- **3 rounds** per match. Placement points per round: `10 / 7 / 5 / 3 / 2 / 1 / 0 / 0 / 0 / 0` — highest total wins the match.
- Grab **coins** to charge a **super fling** (bigger launch, longer cooldown).

## Multiplayer

- **Create Room** → share the 4-letter room code or the `?room=CODE` link with friends.
- Host-authoritative: the host simulates physics, guests just send aim/fling inputs (~25 snapshots/sec).
- The host can add **CPU bots** (`+CPU`) to fill empty slots, or kick them.
- **Practice vs CPU** drops you into a 6-player battle royale against 5 bots — no internet needed beyond the page itself.

## Controls

- **Drag** anywhere to aim (arrow shows direction + power), **release** to fling.
- Works with mouse and touch.

## Run it yourself

No build step, no backend. Just open `index.html` in a browser (internet needed for the PeerJS signalling server that connects players). Or serve it locally:

```bash
npx serve .
# or
python -m http.server 8000
```

## Tech

- Single `index.html` (~2000 lines) + vendored `peerjs.min.js` — that's the whole site.
- Canvas rendering: gradient arena, animated energy boundary, starfield, fighter sprites, particles, screen shake.
- Networking: [PeerJS](https://peerjs.com/) (WebRTC data channels), host-authoritative star topology.

---

Made with 🎯 by shrey & Muse
