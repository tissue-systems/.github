## Tissue Systems

We make two products, and they share one account.

**[Tissue Cloud](https://tissue.systems)** runs a JavaScript or WebAssembly function on a live
URL, with a SQL database, object storage and cron attached. You deploy it with `ribo deploy`.

**[Tissue Mast](https://tissue.systems/mast/)** is uptime monitoring that rings your phone until
you answer. It checks your sites from eight locations, pages you when a cron job stops checking
in, and handles on-call rotations and escalation. The Mast Pager app is free on iPhone and
Android.

Most of the code that runs them is closed. The parts that are useful on their own are open.

### Infrastructure we built and run in production

| Repo | What it does |
|---|---|
| [walship](https://github.com/tissue-systems/walship) | Ships committed libSQL WAL frames over HTTP to a warm replica on another machine. It's the replication behind every c3 database, pulled out into a crate of its own. Rust. |
| [caddy-rqlite-storage](https://github.com/tissue-systems/caddy-rqlite-storage) | Caddy certificate storage on rqlite, so a fleet of Caddy servers shares one certificate store and any of them can answer an ACME challenge. Go. |

### Sending pages to Mast

| Repo | What it does |
|---|---|
| [mast-clients](https://github.com/tissue-systems/mast-clients) | Send a page and wait for the acknowledgement, from Python, JavaScript, Go or Rust |
| [hass-mast](https://github.com/tissue-systems/hass-mast) | Home Assistant integration: page a phone from an automation and act on the answer |
| [terraform-provider-tissue](https://github.com/tissue-systems/terraform-provider-tissue) | Channels, vitals, rotations and escalation policies in Terraform or OpenTofu |
| [mast-claude-plugin](https://github.com/tissue-systems/mast-claude-plugin) | Your phone buzzes when Claude Code is waiting on you |
| [mast-codex-plugin](https://github.com/tissue-systems/mast-codex-plugin) | The same for Codex |
| [mast-status](https://github.com/tissue-systems/mast-status) | Mast's status page, hosted here so it stays up when we don't |

### Building on Tissue Cloud

| Repo | What it does |
|---|---|
| [tissue-examples](https://github.com/tissue-systems/tissue-examples) | Example Cells you can deploy into your own account |
| [demo-cbc-sense](https://github.com/tissue-systems/demo-cbc-sense) | An ESP8266 and a DHT22 reporting temperature to a Cell |

### Fixes we sent upstream

- SeaweedFS [#12225](https://github.com/seaweedfs/seaweedfs/pull/12225): `weed backup` no longer hangs closing a volume it just deleted (merged)
- libSQL [#2306](https://github.com/tursodatabase/libsql/pull/2306): exposes `Connection::wal_disable_checkpoint`, which walship needs (open)

[tissue.systems](https://tissue.systems) · [Cloud docs](https://docs.tissue.systems) · [Mast docs](https://tissue.systems/mast/docs/) · [status](https://tissue.systems/status)
