# afk-av

AFK Alterac Valley to get ranks for WoW Classic.

**Note :** This was my own autoclicker for farming rank in WoW Classic. I release it in public because Blizzard had banned lot of botters and this is now unusable. DO NOT USE IT.

# Guide

1) Install Bartender addon.

2) Login into WoW Classic.

3) Bind your "interact with NPC" touch with "F10" (Escape => Keybinds).

4) Create 3 macros :

## Macro A :

This is a macro to target Kartra to join BG in Orgrimmar.

```
/tar Kartra
```

## Macro B :

This is a macro to join & leave BG.

```
/click BattlefieldFrameJoinButton
/click StaticPopup1Button1
/click WorldStateScoreFrameLeaveButton
/click StaticPopup1Button2
```

## Macro C :

This is the most important macro : prevent you to be AFK in BG.

You can use either a macro : 

- A spell (every player will see you, so it's at your own risk) => HIGH RISK.
- Swap gear (less risky than spell, but player than inspect you can see the pattern) => MIDDLE RISK.
- Find herb or Find ore (work very well, no animation, others players will see nothing) => ZERO RISK.

-----------------------------

5) Create Bartender bar with macro A, macro B, macro C on it. You should use a padding of 0 and put this bar on coordinate 0,0 without snapping (top-left corner of your screen), with the default horizontal axis.

6) Get "afk-bg" version for your OS (only Windows has been tested with 1920x1080 resolution, WoW graphic mode in full-screen windowed).

7) Go into Orgrimmar close as possible to Kartra (Alterac tag Battleground) (coordinates : 79/31).

8) Switch window with ALT+TAB and start "afk-bg" program, then switch back to WoW with ALT+TAB.

9) Enjoy the honor.

# People report me in Battleground for AFK, how to counter that ?

There's no easy way to counter that.

Removing the AFK debuff is done by taking damage or doing damage to a target.

Trigonometry function can be use to move into the game, and then you can program something to attack player or mob, but it's not an easy task to do.

The recommended way to counter AFK report is to have a WeakAura that will play repeated sound so you'll be warned if you are flag, and you can take the control to tag mob or player before being deserter.

# Can Blizzard ban me for using this ?

I used this program for many weeks before the banwave, I didn't get ban.

But on February 2020 they started to ban players, so don't use it and play legit.

There's 4 way they can detect it :

- Warden repeat action : we use a random timer for each action, but the mouse movement are not human.
- Warden fingerprint : since it's publicly available, they can use the fingerprint.
- Hook into WinAPI : they probably don't do it because they'll slowdown the process and cause lot of input lag, but we don't really know with 100% accuracy if they register hook into WinAPI.
- Multiple player report : there's no way to counter that. This bot doesn't require you to sit in Alterac Mountain, but player in BG can report you because you'll sit in AV cave with 0 HK for the whole battleground. If you get lot of multiple report from different battleground, they ban.

Anyway, if you are ban, it's from 1 week to 6 month ban, depends on how they classify the ban (afk is 1 week, bot is 6 month).

# Build

Only x64 OS are supported.

## Linux

1) Install build dependencies.

```sh
apt-get install pkg-config libxdo-dev
```

2) Build.

```sh
cargo build --release --target=x86_64-pc-windows-gnu
```

## Windows

1) Install build dependencies.

```sh
apt-get install gcc-mingw-w64-x86-64 pkg-config

rustup target add x86_64-pc-windows-gnu
```

2) Create a config file in $CARGO_HOME/config (ex : .cargo/config) :

```
[target.x86_64-pc-windows-gnu]
linker = "x86_64-w64-mingw32-gcc"
```

3) Build.

```sh
cargo build --release --target=x86_64-pc-windows-gnu
```

## MacOS

To be determined.
