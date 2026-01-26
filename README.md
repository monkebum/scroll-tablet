# scroll-tablet

## Wayland Tablet Setup

This repo is my personal Linux tablet setup built on Wayland using Sway-scroll.

The whole point of this project is simple.
I wanted a touchscreen plus pen device to actually be usable on Linux without constantly fighting the system.

Everything here works on my hardware right now.
This is not meant to be universal or plug and play.
It is meant to be readable, understandable, and easy to change.

---

## What this setup does

- Touch friendly Sway-scroll environment
- Waybar with tablet focused buttons
- On screen keyboard using wvkbd
- Automatic screen rotation
- Smart Touch system for pen and palm handling
- Config as code workflow using Git

---

## Smart Touch (pen vs touchscreen)

This setup includes a small background script I wrote called **Smart Touch**.

What it does:
- When the pen is detected, touchscreen input is turned off
- When the pen is no longer used, touchscreen input is turned back on after a short delay
- This helps a lot with palm touches while writing or drawing

You control it from Waybar:
- One button turns Smart Touch on or off
- One button cycles the cooldown time from 1 to 5 seconds

This works at the compositor level, not inside a single app.
That means it applies system wide.

---

## Waybar

Waybar is basically the control panel for the tablet.

Right now it has buttons for:
- App menu
- On screen keyboard
- Screen rotation
- Smart Touch controls
- Basic system info like battery and clock

Everything is designed to work with touch only.
No right click required.

---

## Config as code workflow

I do not normally edit the tablet directly.

My workflow looks like this:
- I make changes on my main PC
- I commit everything to this GitHub repo
- The tablet pulls updates using `git pull`
- Configs are symlinked from the repo into `~/.config`

This keeps the tablet clean and avoids config drift over time.

---

## Repo structure (simplified)

- `scroll/` Sway-scroll configuration
- `waybar/` Waybar config and styling
- `scripts/` Helper scripts like Smart Touch
- `wvkbd/` On screen keyboard config

Some machine specific files are intentionally not tracked.

---

## Status

The system is feature complete for now.
I will probably keep improving it slowly instead of rewriting everything.

This repo mainly exists for reference, learning, and future iteration.

---

## Notes

This is a personal setup built around my hardware.
If something looks opinionated, it probably is.
Feel free to copy ideas 
