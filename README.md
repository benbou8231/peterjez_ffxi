# DigTracker (v3.2)

A Windower 4 addon for **Final Fantasy XI** that tracks Chocobo Digging stats, session speeds, item yields, and persistent skill-up intervals across multiple characters.

---

## Features

* **Multi-Character Support**: Saves historical stats per character into `data/<CharacterName>.lua`.
* **Persistent Skill Intervals**: Tracks `Digs Since Last Skill` across logouts and sessions so you never lose your current streak.
* **Live Speed Metrics**: Monitors total session digs, success/failure ratios, and hourly rates (`digs/hr` and `items/hr`).
* **Interval Statistics**: Calculates your average, best, and worst dig intervals between skill-ups, with a dynamic status indicator (`DUE` / `Below Avg`).
* **CSV Logging**: Automatically appends dig records to `logs/dig_history.csv` for detailed auditing.

## Installation

1. Download or clone this repository into your Windower `addons` folder:
   ```text
   Windower4/addons/DigTracker/

2. Ensure the main file is named DigTracker.lua.

3. In-game, load the addon using console:
//lua load digtracker

## Commands
All commands can be run using //dt or //digtracker.

//dt toggle	Shows or hides the HUD overlay.
//dt items	Toggles the list of looted items on the HUD.
//dt lock	Locks/unlocks HUD mouse dragging.
//dt reset session	Resets current session counters, timer, and speed stats.
//dt reset persistent	Clears stored lifetime items, skill intervals, and dig counts.
//dt reset all	Erases both session data and lifetime character records.

## File Structure
data/<CharacterName>.lua: Persistent data store containing total digs, item counts, skill-up history, and current interval progress.
logs/dig_history.csv: Exported log history with timestamps, dig results, items obtained, and skill levels.
