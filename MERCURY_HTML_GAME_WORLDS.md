# MERCURY HTML game - worlds, slots, production URL

## Production

Stable game URL: **https://mercury-hq-game.netlify.app/MERCURY_HTML_GAME.html**
After deploys, do a **hard refresh** before testing.

## Save slots + `mapId`

Each cloud slot can store **`mapId`** so worlds stay separate per slot/account.

| `mapId` | UI label | Notes |
|---------|----------|--------|
| `floating_realm` | World 1: Floating Realm | Full island map in `MERCURY_HTML_GAME.html`: waterfalls, trees, crystals, agent rings, and recover terminal. |
| `void_foundry` | World 2: Void Foundry | Darker second-world placeholder ready for the new map build. It stores a separate `mapId` now, so slot saves can stay split when the real World 2 map is added. |

Unknown `mapId` values normalize to `floating_realm`.

## Home screen

- **Shop** - placeholder alert until cosmetics, props, and map items ship.
- **Empty slots** - map picker; filled slots open directly with stored `mapId`.

## Clearing saves

In **Settings** (home or pause): **Clear slot 1 / 2 / 3** or **Clear all slots (1-3)** removes per-slot `localStorage` keys and the matching Supabase `game_saves` row (`player_id` = `...:slot:n`). Slot 1 also clears legacy keys `mercury_world_save_v1` / `mercury_world_save_v1_backup` and the old cloud row keyed only by account id when applicable.

If you are currently playing the slot you want to clear, use **Save and Quit** first, then clear from home **Settings**. This prevents the old in-memory world from being autosaved back into the slot.
