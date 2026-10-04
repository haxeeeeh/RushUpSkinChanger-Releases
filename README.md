# RushUp SkinChanger

A client-side cosmetic changer for CS2. The cosmetics only alter the appearance of
items on your own screen — other players cannot see the changes, except RushUp
users in the same match when both of you turn on skin sharing. The optional HUD
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
- Cases tab: every container in the game (weapon cases, souvenir packages, sticker /
  patch / pin / music kit capsules, graffiti boxes) by category with search, each with
  its picture, key, odds per grade and an Add button (up to 100 at once, with or without
  keys, or keys only). Added cases show in CS2's own new-item popup the next time the
  inventory opens, and carry the "new"
  tag in the inventory
- What a case drops, set per case: random with the real odds, or something that case
  really holds (its own knives / gloves included) on the Nth case of that kind from now,
  with wear, pattern and StatTrak - that one case only, or every case after it.
  For a terminal: which offer (1-5) of the Nth terminal unsealed it comes as
- Added terminals (Genesis / Dead Hand) unseal into CS2's own offer laptop: five offers
  one by one with the real odds and their market price (a built-in list of what
  terminals offer, `tools/make_terminal_prices.py`), decline for the next, accept to keep it (never sent to
  Steam, free); declining the last one discards the terminal. A reopened laptop shows
  the same offer again
- Open added cases with CS2's own Unlock button and reel, with the real odds (★ from
  the knives / gloves the case names); the case and key are used up and the drop is
  added like any other item. A real case opened with an added key works too. A line in
  your chat says what came out (in a match, only you see it)
- CS2's own sticker tool works on added guns: apply (free placement, real or added
  stickers - an added one is used up), scrape and remove; the gun shows CS2's "updated"
  popup and tag
- CS2's own patch tool works on added agents too: apply and remove
- Trade-up contracts of added guns: the next grade up from one of their collections,
  at their average float, StatTrak kept; Covert trades up to a knife or gloves
- Injecting mid-match keeps the config's loadout: equips the game refuses in a
  match are retried and go on once back in the main menu, and items dropped
  when the game resends its inventory are added back

### HUD / match info
Each item has its own switch on the HUD tab, saved with the config; all are on by
default.
- Hit message in chat: who you hit, for how much and how much they have left
  (local chat, only you see it)
- Damage numbers floating up beside the crosshair, also for the player you are
  spectating; a slider sets their size (10–40 px, 10 by default)
- Team bar at the top: the game's own HP, money, best weapon, grenades, armor
  and defuse-kit panel under every avatar, kept open all round (the game only
  opens it at buy time) and filled in for enemies too
- Scoreboard: enemies' money filled into the money column, and the game's own
  defuse-kit and bomb icons on enemies who carry them
- Bomb timer at the top of the screen: bomb site (A / B), time left with a
  progress bar, and a defuse progress bar that shows whether the defuse will
  finish in time
- Styled after the menu, following the current theme's accent colour
- Skin sharing (on by default): stores your SteamID and your guns (with
  charms), knife, gloves and agent (with patches) for both sides on the RushUp
  server, and puts those of other RushUp users in your match on them — both
  sides need it on. Both sides are stored, so a player's look is right the
  moment teams swap
- In a party lobby, members see your agent, gloves and the weapon on show
  (finish only - no wear, seed or stickers) even without RushUp

### Match
- Auto-accept (on by default): accepts a found match the moment the popup
  shows. It accepts when you are away too, and not joining then counts
  as abandoning the match

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