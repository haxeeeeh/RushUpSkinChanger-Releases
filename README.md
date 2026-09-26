# RushUp SkinChanger

A client-side cosmetic changer for CS2. It only alters the appearance of items on
your own screen — other players cannot see the changes, and it grants no gameplay
advantage.

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
- Sticker placement / positioning
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
- Import a single item from its inspect link
- Edit the patches on an added agent
- The inventory persists through configs

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