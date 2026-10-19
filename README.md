## Wreckfest Gigagrid

Wreckfest caps races at 24 cars. Gigagrid raises that to 64, in singleplayer and in multiplayer, on the stock tracks you already own.

It's an unofficial, experimental patch to the game executable. You don't need any track mods. There's no separate SP or MP version either: one patched client does both, and there's a matching dedicated server for hosting.

# **Files aren't live yet, give me another couple of days to polish my first public release.**

## What it does

- **64-car races.** Lobbies, standings, results, scoreboards and the HUD all handle 64 entries.
- **Automatic start grids.** Most tracks only have 24 grid slots. Gigagrid generates the rest at race start, adding lanes where the track is wide enough, so any stock track that supports generated grids works with a full field.
- **Multiplayer up to 64.** The dedicated server holds 64 slots, fills empty ones with bots, and leaves a slot free so a human can always get in.
- **Fixes for things that broke past 24.** Running more than 24 cars exposed bugs in stock code. Some crashed, and some just misbehaved quietly: lap counting, kicking players, vote-kick counting, load timeouts, and races starting before every car had loaded. Those are all fixed.

The [patch notes](PATCH_NOTES_v1.0_v1.0.1.md) have the full list.

## How it's distributed

We don't ship the game or any of its files. The download has a small launcher, a patch recipe and a list of file hashes. When you install, the launcher reads your own Steam copy of Wreckfest and rebuilds the patched exe from it. Before it changes anything it checks that the result matches the expected hash exactly.

Your Steam install is left alone. Gigagrid installs side by side in `C:\Program Files\Wreckfest Gigagrid` and points at your Steam game data. It keeps its own saves in `%LOCALAPPDATA%\Wreckfest Gigagrid`, and copies your Steam save into them each time you play.

## Requirements

- Wreckfest on Steam, **build 16986367**. The installer refuses any other build. To stop a Steam update from breaking it, set Wreckfest to "Only update this game when I launch it".
- Windows 10. Windows 11 should work, but hasn't been tested yet.
- Steam has to be running to authenticate game ownership.
- **No mods** for multiplayer. The client and server have to match, so keep the mod list empty. Both can have mods running, this is supported, but the default is zero mods on either and the 64-car functionality is native.

## Installing

1. Download the release ZIP and check its SHA-256 against the one on the release page.
2. Extract it and run `Gigagrid.exe`. It finds your Steam Wreckfest on its own.
3. Click Install and accept the admin prompt. It takes a few minutes.
4. Start the game from the **Wreckfest Gigagrid** shortcut.

The launcher isn't signed, so Windows SmartScreen will probably warn you. Click "More info", then "Run anyway".

To update, run the new version's `Gigagrid.exe`, which offers to upgrade your existing install. To uninstall, open the launcher and click Remove. Your Gigagrid saves are kept.

## Hosting a server

The server is the same Wreckfest dedicated server with the matching Gigagrid patch. A sample config ships with these settings:

- 64 max players and 48 bots;
- a 90-second lobby countdown, so all the bot cars have time to load;
- no mods;
- no car restriction.

## Status

This is a playtest build. It has been run a lot with one human and 63 bots, in both singleplayer and multiplayer. It has **not** been tested yet with several humans in one server, on Windows 11, or with Steam libraries on other drives. That's what the current playtests are for.

The patch notes list the known issues. The bigger ones:

- Vote-kick works but its UI looks wrong.
- The server browser shows 64-player servers as 32.
- A few singleplayer changes from the older 64-car SP builds aren't in the combined client yet.

# Please report any issues you find.

## Disclaimer

This is a fan project, not affiliated with or endorsed by Bugbear or THQ Nordic. You need your own legitimate Steam copy of Wreckfest. Use it at your own risk, and back up your saves. Gigagrid only reads your Steam save, but backing up is good practice anyway.
