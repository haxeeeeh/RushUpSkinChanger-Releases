# RushUp SkinChanger

A client-side cosmetic changer for CS2. The cosmetics only alter the appearance of
items on your own screen — other players cannot see the changes. The optional HUD
tab adds match info (hit feedback, extra scoreboard columns, a bomb timer) that is
also shown only to you; each piece can be switched off.

Users receive a single `RushUpSkinChanger-Injector.exe`. On launch it verifies a
licence key, pulls the latest build, and manual-maps it into the game.

## Features

### Weapons
- Weapon skins
- Weapon paint kits
- Wear / float
- Pattern seed
- StatTrak
- StatTrak kill count, counting up with your kills in game
- Custom names
- Default skin support
- Favourite skins, pinned to the top of the skin list
- Weapon images

### Knives
- Knife model changer
- Knife skins
- Wear
- Pattern seed
- StatTrak
- Custom names
- Restore to the original knife on unapply
- Kill feed shows the knife you picked, not the stock one
- Knife images

### Gloves
- Glove model changer
- Glove skins
- Wear
- Pattern seed
- Restore to the original gloves on unapply
- Glove images

### Stickers
- Sticker kit selection
- Up to 5 sticker slots
- Sticker wear
- Sticker rotation
- Sticker scale
- Sticker placement / positioning, measured from the slot the sticker is
  placed from, so imported freely-placed stickers land where the owner put them
- Sticker images

### Charms / keychains
- Charm selection
- Seed
- X / Y / Z positioning
- Charm images

### Agents
- Agent changer (T and CT agents)
- Default agent support
- Agent patches (up to 3), shown in game and in the 3D preview
- Agent voice lines follow the chosen agent (only you hear it)
- Voice preview: play a random line from the agent's voice pack in the menu
- Agent images

### Music kits
- Music kit selection
- StatTrak music kits, counting up with your MVPs in game
- Music kit images

### Collectibles
- Pins, medals and operation coins (challenge / bronze / silver / gold merged)
- Grade picker per family, categorised like the weapons page
- Collectible images

### Inventory / loadout
- Click a card to select, a button to add — nothing is applied by accident
- Added items show up in the game's own inventory and loadout screens and equip
  like any other item
- Browse your added items by category (weapons, knives, gloves, agents, music
  kits, collectibles, other) with per-item apply / unapply
- Import another player's public CS2 inventory by SteamID, including agent
  patches, collectibles, stickers, graffiti, charms, cases and keys, into a
  config of its own named after the profile (e.g. `tw_eeeeh`)
- Recently loaded inventories drop down under the import box, filtered as you
  type; click one to fill it in
- Import a single item from its inspect link
- Edit the patches on an added agent
- The inventory persists through configs
- Injecting mid-match keeps the config's loadout: equips the game refuses in a
  match are retried and go on once back in the main menu, and items dropped
  when the game resends its inventory are added back

### HUD / match info
Each item has its own switch on the HUD tab, saved with the config; all are on by
default.
- Hit message in chat: who you hit, for how much and how much they have left
  (local chat, only you see it)
- Damage numbers floating up beside the crosshair, also for the player you are
  spectating
- Scoreboard: an HP column for every player (in place of the medal column, so
  long names never push it around), each player's weapon (primary, or pistol)
  and grenades, enemies' money filled into the money column, and the
  game's own defuse-kit and bomb icons on enemies who carry them
- Bomb timer at the top of the screen: bomb site (A / B), time left with a
  progress bar, and a defuse progress bar that shows whether the defuse will
  finish in time
- Styled after the menu, following the current theme's accent colour

### 3D model preview
- Weapon preview
- Agent / player preview
- Mouse drag rotation
- Pan
- Zoom
- Reset controls
- Switching between weapon and player previews

### Menu / configuration
- Standalone ImGui menu (toggle with Insert, unload with PageDown)
- Opening the menu in a match goes to the gun or knife in hand
- Rebindable menu and unload keys
- Skin changer tab
- HUD tab
- Settings tab
- Theme editor with theme save / load
- Config save / load / delete
- Skin changer settings persist through configs
- English / Chinese UI toggle
- Automatic scaling to the display resolution

### Injector / delivery
- KeyAuth licence check with HWID lock
- Licence key and local state stored under `HKCU\Software\RushUp` (no loose files)
- Splash lightbox with live download progress
- Auto-update: fetches the latest DLL when the published version differs
- Manual-map injection into `cs2.exe`
- Requires running as administrator

### Misc
- Item schema parsing for weapons, skins, knives, gloves, stickers, charms,
  agents, music kits and collectibles
- Skin / sticker / agent / collectible image loading from the game files
- Unicode player-name rendering (multi-script font fallback)
- All game signatures / patterns centralized in `patterns.h`

## Usage

1. Get a licence key.
2. Put `RushUpSkinChanger-Injector.exe` in its own folder and **add that folder to
   your antivirus exclusions** (Windows Security → Virus & threat protection →
   Exclusions). The injector manual-maps a DLL into the game, which heuristic
   scanners flag on sight; without the exclusion the downloaded DLL gets
   quarantined and the injector keeps reporting *First run - downloading...*
   followed by a download failure.
3. Run `RushUpSkinChanger-Injector.exe` as administrator and accept the risk
   notice.
4. Paste the licence key when prompted (stored after the first successful check).
5. With CS2 running, wait for the splash to report a successful injection.
6. Press **Insert** in-game to open the menu, **PageDown** to unload.

> ⚠️ Tools that modify game memory can be detected by VAC. Account bans are a real
> risk — use at your own discretion, ideally on a test account.


---

This repository only hosts the published builds (injector exe + `version.txt`) that
the auto-updater pulls from. The source code lives elsewhere. Grab the latest exe
from the [Releases](../../releases/latest) page.