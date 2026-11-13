# Wreckfest Gigagrid

<img width="720" height="405" alt="wreckfest-64-car-grid-2s" src="https://github.com/user-attachments/assets/5c07401e-09df-4012-a572-e8550a0c78f8" />

<br>
<br>

<p align="center">
  <a href="https://github.com/BraveDude8/WreckfestGigaGrids/releases/latest">
    <img src="download-button.svg" alt="Download latest release" height="64">
  </a>
  <br>
  <sub><b>Click the button, then click the <code>.zip</code> under "Assets" to download.</b></sub>
</p>



Wreckfest caps races at 24 cars. Gigagrid raises that to 64, in singleplayer and in multiplayer, on every racetrack.

It's an unofficial, experimental patch to the game executable. You don't need any track mods. There's no separate SP or MP version either: one patched client does both, and there's a matching dedicated server for hosting.



## What it does

- **64-car races.** Lobbies, standings, results, scoreboards and the HUD all handle 64 entries.
  
<img width="720"  alt="20261019233242_1" src="https://github.com/user-attachments/assets/23883044-8666-40a6-bd20-d324fed3b921" />
  
- **Automatic start grids.** Most tracks only have 24 grid slots. Gigagrid generates the rest at race start, adding lanes where the track is wide enough, so any stock track that supports generated grids works with a full field.
  
<img width="720"  alt="wreckfest thumbnail 3 small" src="https://github.com/user-attachments/assets/ccc991cf-62f3-412b-9e6d-ba8727bcf7e6" />

If you're playing a mod track with manually placed grid slots, you can choose to override them with automatic grid slots to load up to 64 cars on any mod track.

<img width="480"  alt="image" src="https://github.com/user-attachments/assets/3bd0fc52-f821-4d9c-9b29-c8ad03571722" />

- **Experimental: 128 cars in singleplayer (new in v1.0.6).** A launcher option, "Experimental: 128 cars (single-player only)", lets Custom Events go up to 128 cars. It's off by default, and 64 stays the default. It only changes the game on your PC: online games and the server stay at 64. It isn't supported and may crash, stutter or behave oddly, and you need a strong PC. See the Status table below.

<img width="720" alt="gigagrid 128 car" src="https://github.com/user-attachments/assets/b7d31d81-65ea-442c-a039-feb8b32a13a2" />

- **64-car derbies (new in v1.0.5).** In singleplayer derby events, cars 25-64 now get proper start positions, so you can run a full 64-car derby on the stock arenas. The arena's own start positions are used first. As of v1.0.6, team derby also fills to 64 in singleplayer, and the dedicated server can host derby.
- **New singleplayer options (new in v1.0.6).** A Non-contact option for singleplayer racing modes (Banger, Team Race, Elimination). AI options for singleplayer custom events, all Off by default: AI Ignores Cars, AI Targets Player (with hunting within 50 m), Team Derby 1 vs All, Marked Man, and a Mutators tab in Event Options.
- **Ghost start and stuck-AI reset (new in v1.0.5).** In singleplayer races cars can start as ghosts, so a full grid can spread out instead of piling up at the first corner. Ghosts are see-through and can't be hit. As of v1.0.6, Ghost Start is **Off by default** in Event Options (if you had it saved as On, your setting is kept), and the duration can be set from 1 to 60 seconds (default 15). Ghosts now become solid in a staggered way, so a ghosted pack no longer becomes solid all at once in one place. Online, the server decides when ghosting ends, so every client sees the same thing. AI cars that get stuck are reset automatically, derby included.
- **HUD editor (new in v1.0.5).** The bundled **wf_hud_layout** editor lets you move, resize and hide parts of the race HUD in game. Press <kbd>F8</kbd> in a race to open it, <kbd>F9</kbd> to save and <kbd>F10</kbd> to reload. Your layout applies to every race.
- **Your progress goes back to Steam (new in v1.0.5).** When you close the game normally, Gigagrid copies that session's progress into your Steam save. Your Steam save is backed up first, and every write is checked. Every Play starts from your Steam progress.

- **Other additions (new in v1.0.6).**
  - Race awards on the results screen, with the top three for each award.
  - The laps setting in Custom Event and lobby event settings goes 1, 2, 3 ... 60.
  - "CLIENT PREDICTION TIME" is back in Options > Network, the option from the original 2018 game. "DEFAULT (1800MS)" behaves exactly as before.
  - Nameplate options in Options > Gameplay: "NAMEPLATE DISTANCE", "NAMEPLATE POSITION NUMBER" (race position beside each opponent's name, 1st to 3rd in gold, silver and bronze) and "NAMEPLATE BACKGROUND OPACITY".
  - The two intro logo videos are skipped, and the 3-2-1 countdown and "GO!" have a thin black outline.
  - On the main menu, Tab steps to the next category, the same as E.
  - The launcher has a dark look, a bug report button and an update check, retries a failed save up to 16 times in the same session, and closes on its own after a successful save.
- **Multiplayer with up to 64 real people.** Probably. I haven't tested it with several people yet.
- The dedicated server holds 64 slots, fills empty ones with bots. Keep bots + the most humans you expect + 2 at 64 or less. As of v1.0.6 it hosts racing, derby, derby deathmatch and elimination race, and has a `/gridslot` command to pin a player to a grid slot. Hosting from the game itself is turned off: use the Gigagrid server.
  
  <img width="720" height="405" alt="20261019233141_1" src="https://github.com/user-attachments/assets/30ff44cc-b64a-4ade-9ede-284efb08f309" />
  <img width="720" height="405" alt="20261019233223_1" src="https://github.com/user-attachments/assets/9ae3ff43-2016-43a8-95bc-565726b79911" />
  
- **Replay system rewritten for 64 cars.** A lot of code changes and a few UI changes to make it behave.
  
  <img width="720" height="405" alt="20261019233508_1" src="https://github.com/user-attachments/assets/87ecdba0-4773-405d-a6ff-9be78060d339" />
  
- **Many, many fixes for things that broke past 24 cars.** Running more than 24 cars exposed bugs in stock code. Some crashed, and some just misbehaved quietly. These are all fixed:
  - lap counting;
  - kicking players and vote-kick counting;
  - load timeouts, and races starting before every car had loaded;
  - track voting starting with extra votes for the first track;
  - car parts disappearing in crowded 64-car scenes;
  - cars vanishing more than about 2 km from the track's centre on big tracks. They now stay visible up to 8 km out;
  - the full leaderboard stacking cars 25-64 on top of one another (v1.0.6);
  - HUD race position for cars beyond 24 (v1.0.6);
  - AI targeting for all 64 cars (v1.0.6);
  - events whose start points sit inside sub-scenes, such as Salt Valley 2x, Salt Valley chicken and the Gardemoen arena, not getting full grids at 64 (v1.0.6);
  - online races sometimes skipping straight to results on the client (v1.0.6).

The [patch notes](https://github.com/BraveDude8/WreckfestGigaGrids/releases/latest) have the full list.



## How it's distributed

This repo does not ship the game or any of its files. The download has a small launcher, a patch recipe and a list of file hashes. When you install, the launcher reads your own Steam copy of Wreckfest and rebuilds the patched exe from it. Before it changes anything it checks that the result matches the expected hash exactly.

Your Steam install is left alone. Gigagrid installs side by side in `C:\Program Files\Wreckfest Gigagrid` and points at your Steam game data. It keeps its own working profile in `%LOCALAPPDATA%\Wreckfest Gigagrid`.

As of v1.0.5, saves work both ways:
- Each Play starts from your Steam save.
- When you close the game normally, the session's progress is copied back to Steam. In v1.0.6 this is faster, but it can still take 30 seconds or more.
- Your Steam save is backed up before every write.
- Steam Cloud can stay on. A restore that would delete a Cloud-synced file is refused before anything changes.

Play starts the game straight away. The full file check only runs when you press **Verify files**.



## Requirements

- Wreckfest on Steam, **build 16986367**. The installer refuses any other build. To stop a Steam update from breaking it, set Wreckfest to "Only update this game when I launch it".
- Windows 10. Windows 11 should work, but hasn't been tested yet.
- Steam has to be running to authenticate game ownership.
- A note for mods - standard Wreckfest rules, the client and server have to match, but the Gigagrid client itself is technically not a "mod" so a stock Gigagrid server will list 0 mods.
- Mods follow Steam. Each Play switches Gigagrid to the mods active in Steam Wreckfest, so change mods in Steam before Play. The v1.0.6 server only hosts with no mods: to join, switch every mod off in Steam Wreckfest before Play. The 64-car functionality is native to Gigagrid.
- For the experimental 128-car option: a strong PC. Expect about 13-14 GB of memory in use and a very high GPU load.



## Installing

1. Download `Wreckfest-Gigagrid-v1.0.6.zip`.
2. Extract it and run `Gigagrid.exe`. It finds your Steam Wreckfest on its own.

<img width="608" alt="image" src="https://github.com/user-attachments/assets/d7b828ea-2412-4720-830c-8182cfbc95fe" />


3. Click Install and accept the admin prompt. It takes a few minutes.
4. Start the game from the **Wreckfest Gigagrid** shortcut.

<img width="608" alt="image" src="https://github.com/user-attachments/assets/705e2119-1b3a-4c08-ba95-060227601494" />
  
The launcher isn't signed, so Windows SmartScreen will probably warn you. Click "More info", then "Run anyway".

To update, run the new version's `Gigagrid.exe`, which offers to upgrade your existing install. To uninstall, open the launcher and click Remove. Your Gigagrid saves are kept, and Remove saves your progress first.


## Hosting a server

The server is the same Wreckfest dedicated server with the matching Gigagrid patch. Download `Wreckfest-Gigagrid-Server-v1.0.6.zip`, extract it to a short folder path and run `GigagridServer.exe`. The server instructions on the release page cover install, ports and bots.

- **Version:** everyone must be on v1.0.6. v1.0.5 clients and servers can't join v1.0.6, in either direction.
- **Events:** racing, derby, derby deathmatch and elimination race. Derby on the server is new in v1.0.6 and has only been tested offline. Team modes are refused.
- **Hosting from the game** is turned off in v1.0.6. Use the Gigagrid server.
- **Defaults:**
  - stock gravel racing, 3 laps;
  - 64 max players and 48 bots;
  - a random password;
  - no mods.
- **Bots:** bots + peak humans + 2 must not exceed `max_players`. The in-game Add Bot button stops at 52 of 64. Use the server console's `/bot` command, or Fill bots in the server launcher, to fill further.
- **Grid slots:** `/gridslot` pins a player to a grid slot or clears the pin. It doesn't list, save or reload pins.
- **Ports:** the default query port is **33549**. If you saved a server config with an earlier release and it says `query_port` 27019, change it to 33549.
- **Stopping:** type `exit` in the server console. Exit code `0xC000013A` is a normal stop.



## Status

This is a playtest build. It has been run a lot with one human and 63 bots, in both singleplayer and multiplayer. It has **not** been tested yet with several humans in one server, on Windows 11, or with Steam libraries on other drives. Testing with several humans, over the internet and from another PC is planned for v1.0.7.

# Please report any issues you find.


| Area | Feature | Status | Notes |
|---|---|---|---|
| Capacity | 63 AI + 1 player | **Working** | Tested in singleplayer and multiplayer races. |
| Capacity | 64 AI on a dedicated server | **Working** | Full bot rosters load and operate successfully. |
| Capacity | More than 24 human players in one lobby | Untested | Large AI fields do not verify human connection capacity. |
| Capacity | 64 human players | Untested | Requires a coordinated multiplayer test. |
| Capacity | Multiple humans with AI at 64 total participants | Untested | Confirmed large-field tests used one human player. |
| Capacity | 128 cars in singleplayer | Experimental (v1.0.6) | Launcher option, off by default. Online and the server stay at 64. Not supported; may crash, stutter or behave oddly. |
| Capacity | 128 cars: derby, results, nameplates, position display, replay camera | Not supported | Above 64 cars derby is not supported, and these only cover the first 64 cars. Wreck and assist scoring may be wrong. Nameplate position numbers past 64 are planned for v1.0.7. |
| Capacity | 128 cars: big grids, mod tracks, pit-start tracks | Known issue | Some cars may start in a bad spot; mod tracks may misplace extra cars, so use stock tracks. Some pit-start tracks, such as Dakar, drop cars above their start count. |
| Events | Banger races | **Working** | Multiple large-field races completed successfully. |
| Events | Singleplayer derbies with up to 64 cars | **Working** (v1.0.5) | Cars 25-64 get start positions on stock arenas. Leave Automatic Grid on. |
| Events | Derbies on a server | Further testing needed (v1.0.6) | Derby and derby deathmatch can be hosted. Only tested offline. |
| Events | Derby deathmatch clock on a server | Known issue | The TIME LEFT clock can stay at 02:00. Display only: the match still ends on time and results are filled in. |
| Events | Team derbies | **Working** (v1.0.6) | Fills to 64 in singleplayer. Team modes are refused on the server. |
| Events | Elimination races | **Working** | Works at 64 cars. |
| Events | Team races | **Working** | Works at 64 cars. |
| Events | Last-man-standing variants | Untested | Expanded-field behavior has not been verified. |
| Events | Tag modes | Untested | Expanded-field behavior has not been verified. |
| Events | Career events | Untested | Ghost start is not used in career. Grid sizes, heats and round transitions need verification. |
| Events | Tournament / cup events | Untested | Event progression and rewards need verification. |
| Grids | Expanded automatic race grids | **Working** with limitations | Tested on several tracks; as long as you can physically fit the cars on the track, you're good to go. |
| Grids | Start points inside sub-scenes | **Fixed** (v1.0.6) | Certain tracks with unusual spawns now get full grids at 64. |
| Grids | Preserving sufficient manually authored starts | Further testing needed | Implemented and checked offline; broader gameplay coverage is pending. |
| Grids | Automatic Grid option: On | **Working** | Recommended setting. |
| Grids | Automatic Grid option: Off | **Working** with limitations | Uses stock grid behavior. In derbies the game pauses briefly at the start, and the first derby after switching Off then On can pause once. |
| Grids | Oversized fields with Automatic Grid disabled | **Working** with limitations | Opponent count is limited to the maximum manual grid slot count for that event. |
| Grids | Mod tracks with their own built-in grid | **Working** | Capped at that track's start count, with a warning, unless you switch on automatic grid slots. |
| Grids | Saving the Automatic Grid preference | **Working** | The selected setting persists across restarts. |
| Grids | Rallycross layouts with short starting spurs | **Working** with limitations | Expanded grids can extend off-road and cause placement problems. |
| Grids | All stock tracks and layouts | **Working** with limitations | Works in almost all cases, edge cases like buses on Wrecknado don't quite fit. |
| Grids | All Workshop tracks | **Working** with limitations | Compatibility depends on the track layout and available starts. |
| Grids | All vehicle sizes and mixed fields | **Working** with limitations | Placement needs broader testing with different vehicle dimensions. |
| Multiplayer | Dedicated server install, host, stop and remove | **Working** (v1.0.5) | Tested from the release ZIP, hosting normally and as admin. |
| Multiplayer | v1.0.5 race with 1 human + 63 bots | **Working** | Same-PC join, 3-lap race to results, back to lobby, kicking bots, changing tracks, multiple events in a row. |
| Multiplayer | Joining from another PC over LAN | Untested | Current confirmed connection testing used the same PC. Planned for v1.0.7. |
| Multiplayer | Internet / WAN connections | Untested | External connection testing is planned for v1.0.7. |
| Multiplayer | LAN discovery across different launch orders | Further testing needed | Start the server first, then the client. |
| Multiplayer | Modded client/server compatibility | Not supported | The v1.0.6 server only hosts with no mods. |
| Multiplayer | High-slot participant removal and rejoining | **Working** | Bot removal from high slots tested. Kicking or banning a real player in slot 24+ is untested, especially during an event. |
| Multiplayer | Repeated races and automatic lobby return | **Working** | Passed repeated short-session tests. |
| Multiplayer | Track voting | **Working** (v1.0.5) | The first track no longer starts with extra votes. v1.0.6 also fixes the server's vote counter adding 8 extra votes for the first choice (found in the code, not seen in play). |
| Multiplayer | Vote-kick / vote-ban with multiple humans | Untested | Offline checks passed; successful multiplayer voting needs testing. The vote screen may show wrong numbers, and a ban may not survive a server restart. Admins can use `/kick` and `/ban`. |
| Multiplayer | `/gridslot` | **Working** (v1.0.6) | Sets or clears a pin only. A refused command gives no message. A pin to a slot past the field is accepted, then ignored at the start. |
| Multiplayer | `/cuppointsadjust` for slots 33-64 | **Fixed** (v1.0.6) | Now changes the right car, and no longer forces the points value to an odd number. |
| Multiplayer | Multi-hour / 24-hour hosting | Untested | Long-duration stability testing is pending. |
| Multiplayer | Dedicated server shutdown | **Working** | Type `exit` in the console. |
| Gameplay | Expanded participant-count HUD | **Working** | Verified through manual testing. |
| Gameplay | Full leaderboard with more than 24 cars | **Fixed** (v1.0.6) | Shows 24 rows: the leader, then a window of cars around you. Rows 25-64 no longer stack on one another. |
| Gameplay | HUD editor (F8) | **Working** (v1.0.5) | Tested in singleplayer. In multiplayer it is untested. Its key panel is hidden in exclusive fullscreen. |
| Gameplay | Ghost start | **Working** (v1.0.5) | Singleplayer races; Off by default since v1.0.6. Online in v1.0.6, the server decides when ghosting ends. |
| Gameplay | Stuck-AI reset | **Working** (v1.0.5) | Includes derby. |
| Gameplay | Wrong-way warning fixes | **Working** | Verified through manual testing. |
| Gameplay | Post-race ghosting and flicker fixes | **Working** | Verified through manual testing. |
| Gameplay | Team assignment and scoring above stock limits | **Working** with limitations | Requires dedicated team-mode testing. With 4 teams, the results screen draws the team score boxes over the race award lists (fix planned for v1.0.7). |
| Gameplay | Replay and race restart | **Working** | Replay view cycles between all 64 cars, UI redesigned to handle it. |
| Gameplay | Client prediction time | Known issue | A new setting may only take effect after the next lobby or session load, or a restart. 800 ms can't be chosen; the lowest live setting is 884 ms. |
| Saves | Progress copied back to Steam on close | **Working** (v1.0.5) | Tested on real saves. Faster in v1.0.6, but it can still take 30 seconds or more. A failed save can be retried up to 16 times in the same session, not after a restart. |
| Saves | Automatic v1.0.4 save migration | **Working** (v1.0.5) | A full backup of the v1.0.4 data is kept. |
| Saves | Steam Cloud | **Working** (v1.0.6) | Steam Cloud can stay on. A restore that would delete a Cloud-synced file is refused. |
| Saves | Restoring backups from an earlier install | Known issue | Older backups are listed but can't be restored yet. Planned for v1.0.7. |
| Launcher | Moving or renaming the install folder | Known issue | The Desktop shortcut keeps pointing to the old folder and Windows says "Problem with Shortcut". Move the folder back to fix it. |
| Rendering | Car-part visibility under heavy 64-car load | **Fixed** (v1.0.5) | The renderer has six times as much room for car parts. |
| Rendering | Cars far from the track's centre | **Fixed** (v1.0.5) | Cars stay visible up to 8 km out on big tracks. |
| Rendering | High-DPI / 4K scaled displays | **Fixed** (v1.0.5) | The image is no longer tiled. |
| Rendering | Minimap on big tracks | **Fixed** (v1.0.6) with limitations | Big tracks get eight times the minimap budget. The minimap can sometimes show a detached piece of track or a line that stops short of your car (display only; fix planned for v1.0.7). |
| Performance | Ten-lap 64-car singleplayer races | **Working** | Completed benchmark runs are available, approx 20% framerate loss compared to 24 cars, GPU limited. |
| Performance | 128 cars in singleplayer | Experimental | Expect about 13-14 GB of memory in use and a very high GPU load. |
| Performance | Performance across different tracks and hardware | Further testing needed | Current measurements cover a limited test setup. |



## Disclaimer

This is a fan project, not affiliated with or endorsed by Bugbear or THQ Nordic. You need your own legitimate Steam copy of Wreckfest. Use it at your own risk, and back up your saves. Gigagrid backs up your Steam save before every write, but backing up is good practice anyway.
