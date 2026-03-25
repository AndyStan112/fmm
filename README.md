# fmm
Finite state machine visualizer

Open `index.html` in a browser to use the visualizer.
The FSM is encoded in the URL hash (`#fsm=...`), so you can share the link directly (no DB needed).
You can also load a local `.fsm` file from the UI (`Load .fsm File` button).
You can export:
- `.fsm` text file (`Export .fsm File`)
- Graph image as `.png` (`Export PNG`)

DSL format:
- Line 1 = initial state
- Next lines:
  - `StateName` to start a new state block
  - `(StateName)` to start a final state block
  - `regex -> NewState` for regex transition (`[]` are treated as normal regex characters)
  - `->DefaultState` for default fallback transition
  - Only one default transition is allowed per state block

Docker Compose:
- Start: `docker compose up -d`
- Open HTTP: `http://localhost`
- Open HTTPS: `https://localhost`
- Stop: `docker compose down`

HTTPS notes:
- The compose stack uses Caddy with `tls internal` for local HTTPS out of the box.
- On first use, your browser may warn because the local CA is not yet trusted on your machine.
- Production domain is configured as `windogs.win` (and `www.windogs.win`) in `Caddyfile`.
- Caddy will request trusted Let's Encrypt certificates automatically for that domain when DNS points to this host and ports `80/443` are reachable.
