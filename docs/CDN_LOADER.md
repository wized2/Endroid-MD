# How Endroid-MD originally loaded code

## Public repo (`index.js`)

The GitHub repo does **not** contain the real bot. `index.js` only downloads a remote script:

```js
const url = "https://endroid-cdn.koyeb.app/endroid/endroid-md.js";
const { data } = await axios.get(url);
fs.writeFileSync("cdn-endroid-md.js", data);
require("./cdn-endroid-md.js");
```

## CDN script (`endroid-md.js` from CDN)

That file is **heavily obfuscated**. After decoding, it is a "secure loader" that:

1. Creates decoy folders (`.npm`, `.xcache`, `.files`)
2. Downloads a **ZIP runtime** from the same CDN
3. Extracts it under a deep path resembling:
   `node_modules/yt-search/.config/rashid/.../hidden-files`
4. Spawns `node index.js` in that directory
5. On crash, deletes and re-downloads ("fetching latest version")

## This fork

We captured the extracted runtime and published it **in clear source**:

- All `plugins/*.js` are readable (not obfuscated)
- Categorized under `plugins/{main,group,download,...}/` for navigation
- Flat copies remain in `plugins/` for original `require` paths
- `docs/PLUGIN_INDEX.md` lists command categories

Original upstream: https://github.com/wized2/Endroid-MD  
CDN host observed: `https://endroid-cdn.koyeb.app`
