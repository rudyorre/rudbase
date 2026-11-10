# rudbase.com

Minimalist switchboard index and client-side reachability directory for `*.rudbase.com` and [rudyorre.com](https://rudyorre.com) deployments.

## Architecture

- **Zero backend / static hosting**: Served directly via GitHub Pages with custom domain [`CNAME`](./CNAME) (`rudbase.com`).
- **Startup client probes**: On load (or when pressing `R`), the browser probes each active slot via `fetch(url, { mode: 'no-cors', cache: 'no-store' })` to measure handshake reachability and round-trip latency from the visitor's connection.
- **Keyboard navigation**:
  - `0` — Open operator site (`https://rudyorre.com`)
  - `1`–`7` — Jump directly to the corresponding switchboard slot
  - `R` — Re-run reachability probes
  - `T` — Toggle light/dark theme

## Adding or Editing a Slot

Edit the `SITES` array inside [`index.html`](./index.html). Set `fixedStatus: 'standby'` for planned or in-development subdomains to skip the live browser ping.
