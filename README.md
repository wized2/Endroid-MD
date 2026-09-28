# Endroid-MD

WhatsApp multi-device bot built on Baileys — local plugins, pair-code server, full command suite.

## Features

- Pair-code login (no QR required on server)
- Large plugin pack (download, group, AI, tools, fun, media, …)
- MongoDB optional; works with local/session configs
- Express pair UI + API

## Quick start

```bash
npm install
cp .env.example .env   # set OWNER_NUMBER, PREFIX, etc.
npm start
```

Open the pair page, request a code, enter it in WhatsApp → Linked devices.

## Structure

```
plugins/     # command plugins
lib/         # helpers / DB / events
data/        # data modules
config.js    # bot settings
index.js     # server + runtime entry
endroid-md.js# pair / session router
command.js   # command registry
```

## Config

See `config.js` and `.env.example`. Brand defaults: **Endroid-MD**.

## Commands

See [COMMANDS.md](COMMANDS.md) for the **full** alias list (not unique-only).

Plugins live in `plugins/` (flat) and mirrored under `plugins/{category}/` + `plugins/_all/`.

## License

MIT
