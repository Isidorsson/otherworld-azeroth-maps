# Otherworld_Azeroth 4.4.0

World of Warcraft maps for Hytale at 1 block = 1 yard: the continents, the expansion zones and every dungeon and raid,
classic and retail. Made from WoW client data; not affiliated with Blizzard or Hypixel.

Players joining a server that has this installed don't need to download anything. These files are for running it
on your own Hytale server.

## What this is

A server plugin, `Otherworld_AzerothPlugin`, plus baked map data. Every zip below carries the plugin and the map
data for its own maps.

The maps are **not** saved Hytale worlds. They are our own baked files (terrain tiles, ground textures, buildings),
and the plugin builds the chunks from them as players load them. So you need this plugin: another cubic or world
generation mod can't read these files, and would show empty worlds. The plugin only drives the worlds it creates
(`AzerothWorld` and one world per instance), so it can sit next to your other mods.

What the plugin does:

- Builds the terrain, buildings, water and lava of each map in cubic worlds, at true WoW height.
- Gives every instance its own world, with its entrance spawn point.
- The `/azeroth` command and teleport window, the Dark Portal walk-through to Outland and the Karazhan gate.
- WoW zone lighting: each zone gets its own sky, fog and weather. The light tables, weathers and environments are in
  every zip, so you get them with whatever you download.
- Throws away changed chunks so memory stays flat. Nothing built or broken in these worlds is saved.

## What to download

Get the files from this repo's **Releases** page. Take the ones you want; each works on its own. A bundle that is
too big for one file comes as `-part1`, `-part2`, ...: get every part of it.

| File | What's in it |
|---|---|
| `Azeroth-Eastern-Kingdoms.zip` | Eastern Kingdoms (WoW Forever) |
| `Azeroth-Kalimdor.zip` | Kalimdor (WoW Forever) |
| `Azeroth-Outland.zip` | Outland, Eversong Woods and Azuremyst Isle |
| `Azeroth-Northrend.zip` | Northrend |
| `Azeroth-Eastern-Kingdoms-Retail.zip` | Eastern Kingdoms as it is today (after Cataclysm): Gilneas, Vashj'ir, new Stormwind |
| `Azeroth-Kalimdor-Retail.zip` | Kalimdor as it is today: new Orgrimmar, the flooded Thousand Needles |
| `Azeroth-Outland-Retail.zip`, `Azeroth-Northrend-Retail.zip` | the retail versions of Outland and Northrend |
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

## Install (Hytale server 0.7.7 or newer)

1. Stop the server.
2. In the server folder (the one that has `mods/`), unzip each file you downloaded, in any order:
   `unzip -o Azeroth-Eastern-Kingdoms.zip` and so on. Say yes to overwriting: every zip carries the same small
   plugin files.
3. Start the server. In game, try `/azeroth goldshire`.

To add more maps later, stop the server, unzip the new files the same way and start it again.

Space and memory: the full set is about 23 GB to download and about 87 GB unzipped. Our server runs with a 6 GB Java
heap (`-Xmx6G`); give it at least that if players visit many instances.

## Using the maps in game

- `/azeroth` on its own opens the teleport window: search, filter by type, expansion, continent and zone, and click a
  row to go there.
- `/azeroth <place>` teleports you: a zone, city, town or instance, like `/azeroth goldshire`,
  `/azeroth dornogal` or `/azeroth firelands`.
- `/azeroth list <word>` lists every place whose name has that word.
- Every place name is in [TELEPORTS.md](TELEPORTS.md).

Retail versions sit next to the old ones, with `retail` at the end of a name both have: `/azeroth orgrimmar` and
`/azeroth orgrimmarretail`, `/azeroth deadmines` and `/azeroth deadminesretail`, and so on.

All continents, the retail ones too, share one world, `AzerothWorld`, at true height: you can walk or fly from zone
to zone. Walk through the Dark Portal to reach Outland. Instances are their own worlds: `/azeroth <instance>` takes you
in, and Karazhan also has a walk-in gate in Deadwind Pass. Keep the client render distance moderate in tall
instances.

## Good to know

- Builds don't stick: chunk saving is off in `AzerothWorld` and in the instances, so a chunk resets once players leave.
  Build in your normal worlds.
- Remove an instance: stop the server, delete `mods/Otherworld_AzerothPlugin/instances/<Name>/`.
- Check downloads: `sha256sum -c SHA256SUMS` in the download folder.
- Some retail spots look bare: part of the retail props were not in the client data we baked from.
