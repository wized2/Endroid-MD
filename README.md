# Endroid-MD

WhatsApp multi-device bot with **local, readable plugins** — no remote obfuscated loader required.

## Features

- Full command set organized under `plugins/` (main, group, download, tools, fun, AI, media, …)
- `command.js` registry (`cmd` / `bandah`)
- MongoDB / SQLite helpers in `lib/`
- Pairing UI (`pair.html` + Express entry)

## Quick start

```bash
git clone https://github.com/wized2/Endroid-MD.git
cd Endroid-MD
npm install
cp .env.example .env   # or create .env
# set OWNER_NUMBER, PREFIX, DATABASE_URL / MONGODB_URI
npm start
```

## Config (`.env`)

| Variable | Description |
|----------|-------------|
| `OWNER_NUMBER` | Owner WhatsApp number |
| `PREFIX` | Command prefix (default `.`) |
| `BOT_NAME` | Display name (default Endroid-MD) |
| `DATABASE_URL` / `MONGODB_URI` | Database connection |
| `MENU_IMG` | Menu image URL |

## Layout

```
plugins/          # command plugins (flat + categorized folders)
lib/              # helpers, database, stickers, events
data/             # data modules
docs/             # loader notes + command index
index.js          # Express / pair server entry
command.js        # command registry
config.js         # env config
```

See [docs/PLUGIN_INDEX.md](docs/PLUGIN_INDEX.md) for the command list.

## Credits

Derived from public research on CDN-loaded WhatsApp bot runtimes. Rebranded and maintained as **Endroid-MD**.

## Disclaimer

Educational use. Respect WhatsApp Terms of Service and local laws. You are responsible for how you run this software.
