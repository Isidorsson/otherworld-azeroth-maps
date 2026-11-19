# Otherworld_Azeroth 4.1.0

World of Warcraft maps for Hytale at 1 block = 1 yard. **Private, team only:** this is made from WoW client data, so
never share it publicly.

Players joining a server that has this installed don't need to download anything. These files are for running it
on your own Hytale server.

## What to download

Get the files from this repo's **Releases** page. Take the ones you want; each works on its own. A bundle that is
too big for one file comes as `-part1`, `-part2`, ...: get every part of it.

| File | What's in it |
|---|---|
| `Azeroth-Eastern-Kingdoms.zip` | Eastern Kingdoms (WoW Forever) |
| `Azeroth-Kalimdor.zip` | Kalimdor (WoW Forever) |
| `Azeroth-Outland.zip` | Outland, Eversong Woods and Azuremyst Isle |
| `Azeroth-Northrend.zip` | Northrend |
| `Azeroth-Zones-Cata.zip` | Deepholm, the Lost Isles |
| `Azeroth-Zones-MoP.zip` | Pandaria, the Wandering Isle |
| `Azeroth-Zones-WoD.zip` | Draenor |
| `Azeroth-Zones-Legion.zip` | the Broken Isles, Mardum, Argus |
| `Azeroth-Zones-BfA.zip` | Zandalar, Kul Tiras, Nazjatar |
| `Azeroth-Zones-Shadowlands-part1/2.zip` | the Shadowlands, Zereth Mortis, the Maw |
| `Azeroth-Zones-Dragonflight.zip` | the Dragon Isles, Zaralek Cavern, the Emerald Dream, the Forbidden Reach |
| `Azeroth-Zones-TWW-part1/2/3.zip` | Khaz Algar: the Isle of Dorn and the underground zones, K'aresh |
| `Azeroth-Zones-Midnight.zip` | Harandar, Voidstorm |
| `Azeroth-Instances-Classic.zip`, `-TBC.zip`, `-WotLK.zip` | every dungeon and raid of that expansion (Classic also has the retail remakes of Deadmines, Shadowfang Keep, Scarlet Monastery and Scholomance) |
| `Azeroth-Instances-<Cata, MoP, WoD, Legion, BfA, Shadowlands, Dragonflight, TWW, Midnight>.zip` | retail dungeons and raids, one bundle per expansion (TWW in two parts) |

Retail remakes of classic dungeons are their own worlds next to the old ones: `/azeroth deadmines` and
`/azeroth deadminesretail`, `/azeroth shadowfangkeep` and `/azeroth shadowfangkeepretail`, and so on.

## Install (Hytale server 0.7.7 or newer)

1. Stop the server.
2. In the server folder (the one that has `mods/`), unzip each file you downloaded, in any order:
   `unzip -o Azeroth-Eastern-Kingdoms.zip` and so on. Say yes to overwriting: every zip carries the same small
   plugin files.
3. Start the server. In game, try `/azeroth goldshire`, `/azeroth dornogal`, `/azeroth firelands` or
   `/azeroth list <word>`.
   Every command is in [TELEPORTS.md](TELEPORTS.md).

All continents, the retail ones too, share one world, `AzerothWorld`, at true height. Walk through the Dark Portal to reach Outland.
Instances are their own worlds: `/azeroth <instance>` takes you in, and Karazhan also has a walk-in gate in Deadwind
Pass. Keep the client render distance moderate in tall instances.

- Remove an instance: stop the server, delete `mods/Otherworld_AzerothPlugin/instances/<Name>/`.
- Check downloads: `sha256sum -c SHA256SUMS` in the download folder.
- Builds in `AzerothWorld` are not saved: chunk saving is off there.
