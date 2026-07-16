# DigTracker

A lightweight, robust Windower 4 addon for *Final Fantasy XI* that tracks your Chocobo Digging sessions, persistent historic stats, and calculates your wing skill-up intervals.

This addon uses a custom flat-file Lua database to store items and stats, completely bypassing the buggy XML formatting limitations of the Windower configuration library (meaning no corrupted setting files or HUD crashes!).

---

## Features

* **Session & Lifetime Tracking:** Tracks successful digs, failed digs, total digs, and conquest points earned from beastman resources.
* **Speed & Rate Math:** Calculates your success rates, digs-per-hour, and items-per-hour in real-time.
* **Smart Wing Skill-Up Tracking:** 
  * Records your exact skill level and the number of digs between each skill-up.
  * Calculates your running average, best, and worst intervals.
  * Displays a status indicator (`Below Avg` or `DUE`) based on your current luck.
* **Interactive HUD:** Easily reposition the display anywhere on your screen using your mouse.
* **Safe Flat-File Storage:** Saves your precious historical data to a clean, readable Lua file (`data/stats.lua`) that preserves item names with special characters or spaces.
* **CSV Logging:** Automatically logs every dig outcome to `logs/dig_history.csv` for personal analysis or spreadsheet export.

---

## Installation

1. Click the green **Code** button on GitHub and select **Download ZIP** (or clone this repository).
2. Extract the folder to your Windower installation path:
   `Windower4/addons/`
3. Ensure the folder is named exactly `DigTracker` (and contains `DigTracker.lua`).
4. Load the addon in-game by typing:
   `//lua load digtracker`
   *(To load it automatically on login, add `lua load digtracker` to your Windower `scripts/init.txt` file).*

---

## Commands

Use either `//dt` or `//digtracker` followed by these subcommands:

* `//dt toggle`            - Shows or hides the HUD overlay.
* `//dt items`             - Toggles the session item list on the HUD display.
* `//dt lock`              - Locks or unlocks HUD dragging.
* `//dt reset session`     - Clears current session timers and counts.
* `//dt reset persistent`  - Erases your lifetime stats, items list, and skill intervals.
* `//dt reset all`         - Performs a total wipe of both session and lifetime data.

---

## File Structure

Once loaded, the addon will generate the following files inside your `addons/DigTracker/` folder:

* **`DigTracker.lua`** — The main addon script.
* **`data/settings.xml`** — Stores basic display settings (HUD coordinates, locked state, visibility).
* **`data/stats.lua`** — Stores your lifetime digging statistics and item lists. *Backup this file if you move PCs!*
* **`logs/dig_history.csv`** — Log of every single dig event with timestamps.