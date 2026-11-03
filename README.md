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
  
  <img width="720" height="405" alt="20261019233242_1" src="https://github.com/user-attachments/assets/23883044-8666-40a6-bd20-d324fed3b921" />
  
- **Automatic start grids.** Most tracks only have 24 grid slots. Gigagrid generates the rest at race start, adding lanes where the track is wide enough, so any stock track that supports generated grids works with a full field.
  
  <img width="720" height="405" alt="wreckfest thumbnail 3 small" src="https://github.com/user-attachments/assets/ccc991cf-62f3-412b-9e6d-ba8727bcf7e6" />

  If you're playing a mod track with manually placed grid slots, you can choose to override them with automatic grid slots to load up to 64 cars on any mod track.

  <img width="480" height="270" alt="image" src="https://github.com/user-attachments/assets/3bd0fc52-f821-4d9c-9b29-c8ad03571722" />

- **64-car derbies (new in v1.0.5).** In singleplayer derby events, cars 25-64 now get proper start positions, so you can run a full 64-car derby on the stock arenas. The arena's own start positions are used first.
- **Ghost start and stuck-AI reset (new in v1.0.5).** In singleplayer races every car starts as a ghost, so a full grid can spread out instead of piling up at the first corner. Ghosts are see-through and can't be hit. You can switch it off or set it from 1 to 60 seconds (default 15) in Event Options. AI cars that get stuck are reset automatically, derby included.
- **HUD editor (new in v1.0.5).** The bundled **wf_hud_layout** editor lets you move, resize and hide parts of the race HUD in game. Press <kbd>F8</kbd> in a race to open it, <kbd>F9</kbd> to save and <kbd>F10</kbd> to reload. Your layout applies to every race.
- **Your progress goes back to Steam (new in v1.0.5).** When you close the game normally, Gigagrid copies that session's progress into your Steam save. Your Steam save is backed up first, and every write is checked. Every Play starts from your Steam progress.
- **Multiplayer with up to 64 real people.** Probably. I haven't tested it with several people yet.
- The dedicated server holds 64 slots, fills empty ones with bots, and leaves a slot free so a human can always get in.
  
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
  - cars vanishing more than about 2 km from the track's centre on big tracks. They now stay visible up to 8 km out.

The [patch notes](https://github.com/BraveDude8/WreckfestGigaGrids/releases/tag/Release) have the full list.



## How it's distributed

This repo does not ship the game or any of its files. The download has a small launcher, a patch recipe and a list of file hashes. When you install, the launcher reads your own Steam copy of Wreckfest and rebuilds the patched exe from it. Before it changes anything it checks that the result matches the expected hash exactly.

Your Steam install is left alone. Gigagrid installs side by side in `C:\Program Files\Wreckfest Gigagrid` and points at your Steam game data. It keeps its own working profile in `%LOCALAPPDATA%\Wreckfest Gigagrid`.

As of v1.0.5, saves work both ways:
- Each Play starts from your Steam save.
- When you close the game normally, the session's progress is copied back to Steam.
- Your Steam save is backed up before every write.

Play starts the game straight away. The full file check only runs when you press **Verify files**.



## Requirements

- Wreckfest on Steam, **build 16986367**. The installer refuses any other build. To stop a Steam update from breaking it, set Wreckfest to "Only update this game when I launch it".
- Windows 10. Windows 11 should work, but hasn't been tested yet.
- Steam has to be running to authenticate game ownership.
- A note for mods - standard Wreckfest rules, the client and server have to match, but the Gigagrid client itself is technically not a "mod" so a stock Gigagrid server will list 0 mods.
- Both can have mods running, this is supported, but the default is zero mods on either and the 64-car functionality is native to Gigagrid.



## Installing

1. Download the release ZIP.
2. Extract it and run `Gigagrid.exe`. It finds your Steam Wreckfest on its own.

<img width="676" height="343" alt="image" src="https://github.com/user-attachments/assets/bf8ee79b-b6a5-46c5-937c-2395d249b379" />

3. Click Install and accept the admin prompt. It takes a few minutes.
4. Start the game from the **Wreckfest Gigagrid** shortcut.

  <img width="608" height="259" alt="image" src="https://github.com/user-attachments/assets/aed1bb15-775c-4b35-a6b4-918eee9afb4a" />
  
The launcher isn't signed, so Windows SmartScreen will probably warn you. Click "More info", then "Run anyway".

To update, run the new version's `Gigagrid.exe`, which offers to upgrade your existing install. To uninstall, open the launcher and click Remove. Your Gigagrid saves are kept.


## Hosting a server

The server is the same Wreckfest dedicated server with the matching Gigagrid patch. Download `Wreckfest-Gigagrid-Server-v1.0.5.zip`, extract it to a short folder path and run `GigagridServer.exe`. The server instructions on the release page cover install, ports and bots.

- **Version:** everyone must be on v1.0.5. v1.0.4 clients and servers can't join v1.0.5, in either direction.
- **Events:** racing only. Derby is singleplayer only for now.
- **Defaults:**
  - stock gravel racing, 3 laps;
  - 64 max players and 48 bots;
  - a random password;
  - no mods.
- **Bots:** bots + peak humans + 2 must not exceed `max_players`. The in-game Add Bot button stops at about 25 bots. Use the server console's `/bot` command to fill further.
- **Ports:** the default query port is now **33549**. If you saved a server config with v1.0.4, change `query_port` from 27019 to 33549.
- **Stopping:** type `exit` in the server console. Exit code `0xC000013A` is a normal stop.



## Status

This is a playtest build. It has been run a lot with one human and 63 bots, in both singleplayer and multiplayer. It has **not** been tested yet with several humans in one server, on Windows 11, or with Steam libraries on other drives. That's what the current playtests are for. Derbies do not currently support autogenerated grid slots past 24, but if you manually add more grid slots it'll work.

# Please report any issues you find.


| Area | Feature | Status | Notes |
|---|---|---|---|
| Capacity | 63 AI + 1 player | **Working** | Tested in singleplayer and multiplayer races. |
| Capacity | 64 AI on a dedicated server | **Working** | Full bot rosters load and operate successfully. |
| Capacity | More than 24 human players in one lobby | Untested | Large AI fields do not verify human connection capacity. |
| Capacity | 64 human players | Untested | Requires a coordinated multiplayer test. |
| Capacity | Multiple humans with AI at 64 total participants | Untested | Confirmed large-field tests used one human player. |
| Capacity | More than 64 participants | In development | 128 cars is the target for a later version. |
| Events | Banger races | **Working** | Multiple large-field races completed successfully. |
| Events | Singleplayer derbies with up to 64 cars | **Working** (v1.0.5) | Cars 25-64 get start positions on stock arenas. Leave Automatic Grid on. |
| Events | Derbies on a server | Not supported | The v1.0.5 server is racing-only. |
| Events | Team derbies | Not supported | Team derby still uses the stock grid. |
| Events | Elimination races | Untested | Expanded-field behavior has not been verified. |
| Events | Team races | Untested | Expanded-field placement and team logic need testing. |
| Events | Last-man-standing variants | Untested | Expanded-field behavior has not been verified. |
| Events | Tag modes | Untested | Expanded-field behavior has not been verified. |
| Events | Career events | Untested | Ghost start is not used in career. Grid sizes, heats and round transitions need verification. |
| Events | Tournament / cup events | Untested | Event progression and rewards need verification. |
| Grids | Expanded automatic race grids | **Working** with limitations | Tested on several tracks; as long as you can physically fit the cars on the track, you're good to go. |
| Grids | Automatic fallback when authored starts are insufficient | **Working** with limitations | Supported for ordinary Banger races. Track coverage remains incomplete. |
| Grids | Preserving sufficient manually authored starts | Further testing needed | Implemented and checked offline; broader gameplay coverage is pending. |
| Grids | Automatic Grid option: On | **Working** | Recommended setting. |
| Grids | Automatic Grid option: Off | **Working** with limitations | Uses stock grid behavior. In derbies the game pauses briefly at the start. |
| Grids | Oversized fields with Automatic Grid disabled | **Working** | Opponent count is limited to the maximum manual grid slot count for that event. |
| Grids | Mod tracks with their own built-in grid | **Working** with limitations | Capped at that track's start count, with a warning. |
| Grids | Saving the Automatic Grid preference | **Working** | The selected setting persists across restarts. |
| Grids | Rallycross layouts with short starting spurs | Known issue | Expanded grids can extend off-road and cause placement problems. |
| Grids | All stock tracks and layouts | Further testing needed | Full 64-car coverage has not been established. |
| Grids | All Workshop tracks | Further testing needed | Compatibility depends on the track layout and available starts. |
| Grids | All vehicle sizes and mixed fields | Further testing needed | Placement needs broader testing with different vehicle dimensions. |
| Multiplayer | Dedicated server install, host, stop and remove | **Working** (v1.0.5) | Tested from the release ZIP, hosting normally and as admin. |
| Multiplayer | v1.0.5 race with 1 human + 31 bots | **Working** | Same-PC join, 3-lap race to results, back to lobby, kicking a bot from slot 31. |
| Multiplayer | Join and leave with `max_players` 40 and 63 | **Working** | Same-PC LAN. |
| Multiplayer | Joining from another PC over LAN | Untested | Current confirmed connection testing used the same PC. |
| Multiplayer | Internet / WAN connections | Untested | External connection testing is pending. |
| Multiplayer | LAN discovery across different launch orders | Further testing needed | Start the server first, then the client. |
| Multiplayer | Modded client/server compatibility | Not supported | The v1.0.5 server only hosts with no mods. |
| Multiplayer | High-slot participant removal and rejoining | **Working** | Bot removal from high slots tested. Removing a real player in slot 24+ is untested on v1.0.5. |
| Multiplayer | Repeated races and automatic lobby return | **Working** | Passed repeated short-session tests. |
| Multiplayer | Track voting | **Working** (v1.0.5) | The first track no longer starts with extra votes. |
| Multiplayer | Vote-kick / vote-ban with multiple humans | Untested | Offline checks passed; successful multiplayer voting needs testing. |
| Multiplayer | Multi-hour / 24-hour hosting | Untested | Long-duration stability testing is pending. |
| Multiplayer | Dedicated server shutdown | **Working** | Type `exit` in the console. |
| Gameplay | Expanded participant-count HUD | **Working** | Verified through manual testing. |
| Gameplay | HUD editor (F8) | **Working** (v1.0.5) | Tested in singleplayer. In multiplayer it is untested. Its key panel is hidden in exclusive fullscreen. |
| Gameplay | Ghost start | **Working** (v1.0.5) | Singleplayer races. Multiplayer is unchanged. |
| Gameplay | Stuck-AI reset | **Working** (v1.0.5) | Includes derby. |
| Gameplay | Wrong-way warning fixes | **Working** | Verified through manual testing. |
| Gameplay | Post-race ghosting and flicker fixes | **Working** | Verified through manual testing. |
| Gameplay | Vehicle resets and early-finisher behavior | Further testing needed | Physical-control checks remain incomplete. |
| Gameplay | Timers, pickups and scoring for slots 25–64 | Further testing needed | Full high-slot gameplay coverage is pending. |
| Gameplay | Team assignment and scoring above stock limits | Untested | Requires dedicated team-mode testing. |
| Gameplay | Replay and race restart | **Working** | Replay view cycles between all 64 cars, UI redesigned to handle it. |
| Saves | Progress copied back to Steam on close | **Working** (v1.0.5) | Tested on real saves. Saving can take 30 seconds or more; faster saving is planned. |
| Saves | Automatic v1.0.4 save migration | **Working** (v1.0.5) | A full backup of the v1.0.4 data is kept. |
| Saves | Restoring backups from an earlier install | Known issue | Older backups are listed but can't be restored yet. |
| Rendering | Car-part visibility under heavy 64-car load | **Fixed** (v1.0.5) | The renderer has six times as much room for car parts. |
| Rendering | Cars far from the track's centre | **Fixed** (v1.0.5) | Cars stay visible up to 8 km out on big tracks. |
| Rendering | High-DPI / 4K scaled displays | **Fixed** (v1.0.5) | The image is no longer tiled. |
| Performance | Ten-lap 64-car singleplayer races | **Working** | Completed benchmark runs are available, approx 20% framerate loss compared to 24 cars, GPU limited. |
| Performance | Performance across different tracks and hardware | Further testing needed | Current measurements cover a limited test setup. |



## Disclaimer

This is a fan project, not affiliated with or endorsed by Bugbear or THQ Nordic. You need your own legitimate Steam copy of Wreckfest. Use it at your own risk, and back up your saves. Gigagrid only reads your Steam save, but backing up is good practice anyway.
