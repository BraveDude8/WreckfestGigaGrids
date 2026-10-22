# Wreckfest Gigagrid

<img width="720" height="405" alt="wreckfest-64-car-grid-2s" src="https://github.com/user-attachments/assets/5c07401e-09df-4012-a572-e8550a0c78f8" />



Wreckfest caps races at 24 cars. Gigagrid raises that to 64, in singleplayer and in multiplayer, on every racetrack.

It's an unofficial, experimental patch to the game executable. You don't need any track mods. There's no separate SP or MP version either: one patched client does both, and there's a matching dedicated server for hosting.



## What it does

- **64-car races.** Lobbies, standings, results, scoreboards and the HUD all handle 64 entries.
  
  <img width="720" height="405" alt="20261019233242_1" src="https://github.com/user-attachments/assets/23883044-8666-40a6-bd20-d324fed3b921" />
  
- **Automatic start grids.** Most tracks only have 24 grid slots. Gigagrid generates the rest at race start, adding lanes where the track is wide enough, so any stock track that supports generated grids works with a full field.
  
  <img width="720" height="405" alt="wreckfest thumbnail 3 small" src="https://github.com/user-attachments/assets/ccc991cf-62f3-412b-9e6d-ba8727bcf7e6" />

  If you're playing a mod track with manually placed grid slots, you can choose to override them with automatic grid slots to load up to 64 cars on any mod track.

  <img width="480" height="270" alt="image" src="https://github.com/user-attachments/assets/3bd0fc52-f821-4d9c-9b29-c8ad03571722" />
  
- **Multiplayer with up to 64 real people.** Probably. I haven't tested it yet.
- The dedicated server holds 64 slots, fills empty ones with bots, and leaves a slot free so a human can always get in.
  
  <img width="720" height="405" alt="20261019233141_1" src="https://github.com/user-attachments/assets/30ff44cc-b64a-4ade-9ede-284efb08f309" />
  <img width="720" height="405" alt="20261019233223_1" src="https://github.com/user-attachments/assets/9ae3ff43-2016-43a8-95bc-565726b79911" />
  
- **Replay system rewritten for 64 cars.** A lot of code changes and a few UI changes to make it behave.
  
  <img width="720" height="405" alt="20261019233508_1" src="https://github.com/user-attachments/assets/87ecdba0-4773-405d-a6ff-9be78060d339" />
  
- **Many, many fixes for things that broke past 24 cars.** Running more than 24 cars exposed bugs in stock code. Some crashed, and some just misbehaved quietly: lap counting, kicking players, vote-kick counting, load timeouts, and races starting before every car had loaded. Those are all fixed.

The [patch notes](https://github.com/BraveDude8/WreckfestGigaGrids/releases/tag/Release) have the full list.



## How it's distributed

This repo does not ship the game or any of its files. The download has a small launcher, a patch recipe and a list of file hashes. When you install, the launcher reads your own Steam copy of Wreckfest and rebuilds the patched exe from it. Before it changes anything it checks that the result matches the expected hash exactly.

Your Steam install is left alone. Gigagrid installs side by side in `C:\Program Files\Wreckfest Gigagrid` and points at your Steam game data. It keeps its own saves in `%LOCALAPPDATA%\Wreckfest Gigagrid`, and copies your Steam save into them each time you play. In the future it'll probably copy progress back on shutdown, I'm just being cautious for now.



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

The server is the same Wreckfest dedicated server with the matching Gigagrid patch. A sample config ships with these settings:

- 64 max players and 48 bots;
- a 90-second lobby countdown, so all the bot cars have time to load;
- no mods;
- no car restriction.



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
| Capacity | More than 64 participants | Untested | Next milestone will be 96, paused at 64 for stability/refinement for now. |
| Events | Banger races | **Working** | Multiple large-field races completed successfully. |
| Events | Derbies with sufficient manually authored starts | **Working** | Tested with 64 cars on an arena containing 64 starts. |
| Events | Expanded derbies without sufficient manually authored starts | Not working | Automatic grid expansion does not currently support derbies. |
| Events | Elimination races | Untested | Expanded-field behavior has not been verified. |
| Events | Team races | Untested | Expanded-field placement and team logic need testing. |
| Events | Team derbies / team deathmatch | Untested | Expanded-field behavior has not been verified. |
| Events | Last-man-standing variants | Untested | Expanded-field behavior has not been verified. |
| Events | Tag modes | Untested | Expanded-field behavior has not been verified. |
| Events | Career events | Untested | Grid sizes, heats and round transitions need verification. |
| Events | Tournament / cup events | Untested | Event progression and rewards need verification. |
| Grids | Expanded automatic race grids | **Working** with limitations | Tested on several tracks; as long as you can physically fit the cars on the track, you're good to go. |
| Grids | Automatic fallback when authored starts are insufficient | **Working** with limitations | Supported for ordinary Banger races. Track coverage remains incomplete. |
| Grids | Preserving sufficient manually authored starts | Further testing needed | Implemented and checked offline; broader gameplay coverage is pending. |
| Grids | Automatic Grid option: On | **Working** | Corrected behavior verified on Tribend Main Circuit. |
| Grids | Automatic Grid option: Off | **Working** | Uses stock grid behavior while retaining the selected opponent count. |
| Grids | Oversized fields with Automatic Grid disabled | **Working** | Opponent count is limited to the maximum manual grid slot count for that event. |
| Grids | Saving the Automatic Grid preference | **Working** | The selected setting persists across restarts. |
| Grids | Rallycross layouts with short starting spurs | Known issue | Expanded grids can extend off-road and cause placement problems. |
| Grids | All stock tracks and layouts | Further testing needed | Full 64-car coverage has not been established. |
| Grids | All Workshop tracks | Further testing needed | Compatibility depends on the track layout and available starts. |
| Grids | All vehicle sizes and mixed fields | Further testing needed | Placement needs broader testing with different vehicle dimensions. |
| Multiplayer | Dedicated server startup and local joining | **Working** | Verified with the current client/server pair. |
| Multiplayer | v1.0.4 race with 1 human + 63 AI | **Working** | Race completed successfully. |
| Multiplayer | v1.0.4 leave and rejoin | **Working** | Confirmed through manual testing. |
| Multiplayer | Joining from another PC over LAN | Untested | Current confirmed connection testing used the same PC. |
| Multiplayer | Internet / WAN connections | Untested | External connection testing is pending. |
| Multiplayer | LAN discovery across different launch orders | Further testing needed | Server-first discovery worked; other launch orders need verification. |
| Multiplayer | Modded client/server compatibility | Further testing needed | Matching mod configurations need broader testing. |
| Multiplayer | High-slot participant removal and rejoining | **Working** | Controlled tests passed after fixing a high-slot removal crash. |
| Multiplayer | Repeated races and automatic lobby return | **Working** | Passed repeated short-session tests. |
| Multiplayer | Vote-kick / vote-ban with multiple humans | Untested | Offline checks passed; successful multiplayer voting needs testing. |
| Multiplayer | Multi-hour / 24-hour hosting | Untested | Long-duration stability testing is pending. |
| Multiplayer | Dedicated server shutdown | Further testing needed | Manual testing passed, but an automated shutdown result still needs reconciliation. |
| Gameplay | Expanded participant-count HUD | **Working** | Verified through manual testing. |
| Gameplay | Wrong-way warning fixes | **Working** | Verified through manual testing. |
| Gameplay | Post-race ghosting and flicker fixes | **Working** | Verified through manual testing. |
| Gameplay | Vehicle resets and early-finisher behavior | Further testing needed | Physical-control checks remain incomplete. |
| Gameplay | Timers, pickups and scoring for slots 25–64 | Further testing needed | Full high-slot gameplay coverage is pending. |
| Gameplay | Team assignment and scoring above stock limits | Untested | Requires dedicated team-mode testing. |
| Gameplay | Replay and race restart | **Working** | Replay view cycles between all 64 cars, UI redesigned to handle it. |
| Rendering | Car-part visibility under heavy 64-car load | Known issue | A targeted fix passed testing and is planned for v1.0.5. |
| Performance | Ten-lap 64-car singleplayer races | **Working** | Completed benchmark runs are available, approx 20% framerate loss compared to 24 cars, GPU limited. |
| Performance | Performance across different tracks and hardware | Further testing needed | Current measurements cover a limited test setup. |


## Disclaimer

This is a fan project, not affiliated with or endorsed by Bugbear or THQ Nordic. You need your own legitimate Steam copy of Wreckfest. Use it at your own risk, and back up your saves. Gigagrid only reads your Steam save, but backing up is good practice anyway.
