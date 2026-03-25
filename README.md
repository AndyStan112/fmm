# fmm
Finite state machine visualizer

Open `index.html` in a browser to use the visualizer.
The FSM is encoded in the URL hash as Base64URL (`#fsm64=...`) so you can share it directly.
You can also load a local `.fsm` file from the UI (`Load .fsm File` button).
You can export:
- `.fsm` text file (`Export .fsm File`)
- Graph image as `.png` (`Export PNG`)

DSL format:
- Line 1 = initial state
- Next lines:
  - `StateName` to start a new state block
  - `(StateName)` to start a final state block
  - `regex -> NewState` for regex transition
  - `->DefaultState` for default fallback transition
  - Only one default transition is allowed per state block

Docker Compose:
- Start: `docker compose up -d`
- Open HTTP: `http://localhost`
- Open HTTPS: `https://localhost`
- Stop: `docker compose down`
