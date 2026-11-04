# DigTracker (v3.3.1)

A Windower 4 addon for **Final Fantasy XI** that tracks Chocobo Digging stats, session speeds, item yields, and persistent skill-up intervals across multiple characters.

---

## Features

* **Multi-Character Support**: Saves historical stats per character into `data/<CharacterName>.lua`.
* **Persistent Skill Intervals**: Tracks `Digs Since Last Skill` across logouts and sessions so you never lose your current streak.
* **Live Speed Metrics**: Monitors total session digs, success/failure ratios, and hourly rates (`digs/hr` and `items/hr`).
* **Interval Statistics**: Calculates your average, best, and worst dig intervals between skill-ups, with a dynamic status indicator (`DUE` / `Below Avg`).
* **CSV Logging**: Automatically appends dig records to `logs/dig_history.csv` for detailed auditing.

## Fork Improvements

This fork extends the original DigTracker by [peterjez](https://github.com/peterjez/ffxi/tree/main/digtracker) with:

- **Chocobo-only tracking:** Only processes dig-result messages while riding a chocobo, reducing false counts.
- **Regional currency tracking:** Separately tracks Conquest Points, Imperial Standing, Allied Notes, and Bayld.
- **Alphabetical loot ordering:** Consistent item ordering in the HUD and saved records.

See the [Changelog](CHANGELOG.md) for the complete version history.

## Installation

1. Download the repository and copy its `digtracker` folder into your Windower addons directory:
   `Windower4/addons/digtracker/`

2. Ensure the addon file is located at:
   `Windower4/addons/digtracker/digtracker.lua`

3. Load the addon in-game using:
   `//lua load digtracker`

## Commands
All commands can be run using //dt or //digtracker.

**//dt toggle**	         Shows or hides the HUD overlay.<br>
**//dt items**	            Toggles the list of looted items on the HUD.<br>
**//dt lock**	            Locks/unlocks HUD mouse dragging.<br>
**//dt reset session**	   Resets current session counters, timer, and speed stats.<br>
**//dt reset persistent**	Clears stored lifetime items, skill intervals, and dig counts.<br>
**//dt reset all**	      Erases both session data and lifetime character records.<br>

## File Structure
**data/<CharacterName>.lua**: Persistent data store containing total digs, item counts, skill-up history, and current interval progress.<br>
**logs/dig_history.csv**: Exported log history with timestamps, dig results, items obtained, and skill levels.
