# DigTracker (v3.5.0)

A Windower 4 addon for **Final Fantasy XI** that tracks Chocobo Digging stats, session speeds, item yields, and persistent skill-up intervals across multiple characters.

---

## Features

* **Multi-Character Support**: Saves historical stats per character into `data/<CharacterName>.lua`.
* **Persistent Skill Intervals**: Tracks total and successful digs since the last skill-up across logouts and sessions.
* **Live Speed Metrics**: Monitors total session digs, success/failure ratios, and hourly rates (`digs/hr` and `items/hr`).
* **Interval Statistics**: Displays a rolling average of the last five completed skill-up intervals, the last three intervals and their successful-dig counts, and the current deviation from the average.
* **CSV Logging**: Automatically appends dig records to `logs/dig_history.csv` for detailed auditing.

## Fork Improvements

This fork extends the original DigTracker by [peterjez](https://github.com/peterjez/ffxi/tree/main/digtracker) with:

- **Chocobo-only tracking:** Only processes dig-result messages while riding a chocobo, reducing false counts.
- **Regional currency tracking:** Separately tracks Conquest Points, Imperial Standing, Allied Notes, and Bayld.
- **Alphabetical loot ordering:** Consistent item ordering in the HUD and saved records.
- **Recent skill-up statistics:** Rolling five-interval average, last three intervals in chronological order, and number of digs above or below the average.
- **Skill-up success history:** Records successful digs for each skill-up interval and displays recent counts alongside existing interval statistics.

See the [Changelog](CHANGELOG.md) for the complete version history.

## Installation

1. Download the repository and copy its `digtracker` folder into your Windower addons directory:
   
   `Windower4/addons/digtracker/`

2. Ensure the addon file is located at:
   
   `Windower4/addons/digtracker/digtracker.lua`

3. In-game, load the addon using console:
   
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
**data/<CharacterName>.lua**: Persistent data store containing dig totals, item counts, skill-up history (total and successful digs), and current interval progress.<br>
**logs/dig_history.csv**: Exported log history with timestamps, dig results, items obtained, and skill levels.

## Credits

- **Original author:** [peterjez](https://github.com/peterjez)
- **Fork maintainer:** [benbou8231](https://github.com/benbou8231)
