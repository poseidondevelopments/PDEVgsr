# Poseidon GSR

A simple and efficient Gunshot Residue (GSR) detection system for FiveM servers. This script allows police officers to test players for gunshot residue, with automatic detection when weapons are fired and realistic fade/wash mechanics.

## Features

- 🔫 **Automatic GSR Detection** - Automatically detects when players fire weapons using ox_inventory integration
- 🧪 **GSR Testing** - Police officers can test players for gunshot residue using ox_target
- ⏱️ **Time-Based Fade** - GSR automatically fades after a configurable amount of time (default: 30 minutes)
- 💧 **Water Wash-Off** - GSR can be washed off in water after a shorter duration (default: 0.5 minutes)
- 👮 **Job Restriction** - Only players with the 'police' job can perform GSR tests
- 📱 **Notifications** - Clean notifications using ox_lib when GSR fades or is washed off

## Dependencies

This script requires the following resources:

- **[ox_lib](https://github.com/overextended/ox_lib)** - For notifications and shared utilities
- **[ox_target](https://github.com/overextended/ox_target)** - For player interaction system
- **[ox_inventory](https://github.com/overextended/ox_inventory)** - For weapon firing detection

## Installation

1. Download and extract the script to your `resources` folder
2. Ensure all dependencies (ox_lib, ox_target, ox_inventory) are installed and started
3. Add `ensure poseidon-gsr` to your `server.cfg`
4. Configure the script in `config.lua` (optional)
5. Restart your server or start the resource manually

## Configuration

Edit `config.lua` to customize the script behavior:

```lua
Config.clearGSR = 30        -- Time in minutes for GSR to fade naturally
Config.clearGSRinWater = 0.5 -- Time in minutes for GSR to wash off in water
```

### Configuration Options

- **`Config.clearGSR`** - The time (in minutes) it takes for GSR to naturally fade from a player. Default: `30` minutes
- **`Config.clearGSRinWater`** - The time (in minutes) it takes for GSR to be washed off when a player is in water. Default: `0.5` minutes

## Usage

### For Players

- GSR is automatically detected when you fire a weapon
- GSR will fade naturally after the configured time period
- Entering water will wash off GSR faster (after the configured water time)
- You'll receive a notification when GSR fades or is washed off

### For Police Officers

1. Approach any player
2. Use ox_target to interact with them
3. Select "GSR TEST" from the interaction menu
4. You'll receive a notification indicating:
   - **POSITIVE** - Player has fired a weapon recently
   - **NEGATIVE** - Player has not fired a weapon (or GSR has faded)

## How It Works

1. When a player fires a weapon, the script detects it via `ox_inventory:updateWeapon` event
2. The player's state is set to `shot = true` with a timestamp
3. Police officers can test players using ox_target interaction
4. GSR automatically fades after the configured time
5. If a player enters water while having GSR, it washes off faster

## Support & Updates

Join the Poseidon Developments Discord for:
- 🆕 Script announcements and updates
- 🛠️ Support and bug reports
- 📦 Other scripts, conversions, and code snippets

**[Join Discord](https://discord.gg/3w8bdfZusD)**

## Credits

- **Developer:** Poseidon Developments
- **Script Name:** Poseidon GSR
- **Version:** Compatible with FiveM (cerulean)

## License

This script is provided as-is. Please respect the developer's work and do not redistribute without permission.

---

**Made with ❤️ by Poseidon Developments**
