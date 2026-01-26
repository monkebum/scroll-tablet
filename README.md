# scroll-tablet

# Wayland Tablet Setup

This repo contains the configuration I use to run a Linux tablet on Wayland with Sway.

The goal of this setup is simple:
make a touchscreen + pen device actually usable on Linux without constant fighting.

Everything here works on my system today. It is not meant to be universal or plug and play, but it is meant to be readable, adaptable, and stable.

---

## What this setup does

- Touch friendly Sway environment
- Waybar with tablet focused buttons
- On screen keyboard using wvkbd
- Automatic screen rotation
- Smart Touch system for palm rejection
- Config as code workflow using Git

---

## Smart Touch (pen vs touchscreen)

This setup includes a small background script called **Smart Touch**.

What it does:
- When the pen is detected, touchscreen input is disabled
- When the pen is no longer used, touchscreen input is re enabled after a short delay
- This greatly reduces palm touches while writing or drawing

You can control it from Waybar:
- One button toggles Smart Touch on or off
- One button cycles the cooldown time from 1 to 5 seconds

This works at the compositor level, not inside a single app, so it applies system wide.

---

## Waybar

Waybar is used as the main control surface for tablet actions.

Current buttons include:
- App menu
- On screen keyboard toggle
- Screen rotation
- Smart Touch controls
- System info like battery and clock

Everything is designed to be usable with touch only.

---

## Config as code workflow

This tablet is not edited directly most of the time.

The workflow is:
- All changes are made on a main PC
- Changes are committed to this GitHub repo
- The tablet pulls updates using `git pull`
- Configs are symlinked from the repo into `~/.config`

This keeps the tablet clean and avoids config drift.

---

## Repo structure (simplified)

- `sway/` Sway configuration
- `waybar/` Waybar config and styling
- `scripts/` Helper scripts like Smart Touch
- `wvkbd/` On screen keyboard config

Some machine specific files are intentionally not tracked.

---

## Status

The system is feature complete for now.
Future changes will be incremental improvements, not rewrites.

This repo is mainly here for reference, learning, and future iteration.

---

## Notes

This is a personal setup built around my hardware.
If something looks opinionated, it probably is.
Feel free to copy ideas, not blindly copy files.
