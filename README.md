# Otherworld_Azeroth 4.0.0

World of Warcraft maps for Hytale at 1 block = 1 yard. **Private, team only:** this is made from WoW client data, so
never share it publicly.

Players joining a server that has this installed don't need to download anything. These files are for running it
on your own Hytale server.

## What to download

Get the files from this repo's **Releases** page.

| File | When |
|---|---|
| `Core-install-first.zip` | always (plugin, light blocks, place list) |
| `Continent-<name>.zip` | the continents you want; take every part of a split one |
| `Instance-<Classic, TBC or WotLK>-<name>.zip` | any dungeons and raids you want, one folder each |

## Install (Hytale server 0.7.7 or newer)

1. Stop the server.
2. In the server folder (the one that has `mods/`), unzip Core first, then the rest:
   `unzip -o Core-install-first.zip`, then `unzip -o Continent-Eastern-Kingdoms.zip` and so on.
3. Start the server. In game, try `/azeroth goldshire`, `/azeroth karazhan` or `/azeroth list <word>`.
   Every command is in [TELEPORTS.md](TELEPORTS.md).

All continents share one world, `AzerothWorld`, at true height. Walk through the Dark Portal to reach Outland.
Instances are their own worlds: `/azeroth <instance>` takes you in, and Karazhan also has a walk-in gate in Deadwind
Pass. Keep the client render distance moderate in tall instances.

- Remove an instance: stop the server, delete `mods/Otherworld_AzerothPlugin/instances/<Name>/`.
- Check downloads: `sha256sum -c SHA256SUMS` in the download folder.
- Builds in `AzerothWorld` are not saved: chunk saving is off there.
