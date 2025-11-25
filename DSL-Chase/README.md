# DSL Chase

The DSL Chase module allows for automatic chasing of targeted characters and clans during PVP.

DSL Chase was written and tested on Mudlet 4.19.1.

## Installation

Verify gmcp is enabled on your characters by typing the command `gmcp` in DSL if needed. To install the DSL Chase module, download [DSL-Chase.xml](DSL-Chase.xml) and in Mudlet go to Toolbox -> Module Manager -> Install to install the module. If you wish to make updates to the script itself for updating any of the configuration options, be sure to click the "sync" checkbox in the module manager.

## Configuration

Configuration for DSL Chase is not necessary, but will make it easier to use by allowing for default configurations to be set for each character without having to set them manually.

To configure a character, with the module installed in "sync" mode update the following at the top of the file for each character needed. The following configuration can be put into a separate script if desired as well instead of updated in the module itself.

```lua
dsl = dsl or {}
dsl.characters = dsl.characters or {}

-- Repeat the following configuration for each character needed
-- The below configuration can be placed into a separate script file
-- outside of this module if desired.
dsl.characters["Ulyssus"] = dsl.characters["Ulyssus"] or {}
dsl.characters["Ulyssus"].chase = {
  command = "c acid", -- The default command to use to attack
  ranged = false, -- Whether ranged mode is enabled by default
  rangedCommand = "c fireball", -- The command to use with ranged modes
  rangedDistance = 3, -- The room distance of the ranged attack
  rangedFinish = true, -- Default value for ranged finish mode
  rangedMove = true, -- Whether to move away in opposite direction before ranging
  minimumHp = 350, -- The minimum HP in which to stop automatically chasing
  extendedScanning = true, -- Enables scanning in all open directions
  clans = {}, -- Default clans to target
}
```

## Usage & Features

DSL Chase has many features and modes.

Type `chase` to see the current state and settings of the chase module. If you are currently fighting an opponent and wish to begin chasing them, type `chase` while fighting and it will enable the module and add your current opponent to the list of characters to chase.

To begin chasing a specific character, use `chase <character name>` which will turn on chasing if it is turned off and add the provided character to the list of characters to chase. You can also chase all characters in a specific clan by typing `chase <clan name` which will check whoc to gather the list of current characters in the clan, and any time whoc is checked it will automatically add additional characters to the list that it finds for that clan.

Type `chase on` or `chase off` to toggle Chase on or off.

`chase help` can be used to see all of the available commands for the chase module.

`chase clear` will clear out the entire list of chased characters and clans.

`chase min` can be used to unset the minimum HP required to chase, allowing you to chase up to death. `chase min <minimum hp>` can be used to set the minimum HP at which chasing will stop when the minimum HP limit is passed.

`chase command <command>` will set the command to use when chasing a character. This command is used when the target is in the current room as your character.

`chase ranged` is used to toggle the ranged mode on or off. Ranged mode is used to use your ranged command to attack from a distance such as using 'c fireball' as the command or 'charge' as the command. This mode will contiually attack the target from distance when enabled. The command `chase ranged distance <distance>` will set the distanced of your ranged command, such as '3' for the command 'c fireball' for a max distance of 3 rooms. Ranged mode also has the command `chase ranged move` which enables moving away from your target when ranging. If your target is west and your character has an open room to the east and has not reached the max distanced of your ranged command, this will move your character away one room before each ranged attack until the max distanced is achieved.

`chase add <character or clan` can be used to add additional characters or clans to the list to be chased.

`chase extended` enables or disables the extended scanning mode. By default Chase will scan once when chasing. If no target is found, extended scanning will then scan in each available direction one at a time looking for any targets further away with this mode is enabled.

`chase debug` turns on debug mode which can be useful in finding any issues with the module.
