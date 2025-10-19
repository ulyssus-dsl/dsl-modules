# DSL Auto-Regen

The DSL Auto-Regen module allows Conclave CSRs to automatically cast regeneration on fellow Conclave members while within the Conclave Common Room. This module uses DSL's gmcp protocol (Generic Mud Communication Protocol) to detect the character's name, mana, AFK status, the current room, and ticks. When a configured CSR enters the Conclave Common Room with the Auto-Regen module enabled, it will create triggers and events that watches for Conclave members entering/leaving the commons and will handle glancing at them, linking, and regenerating them as needed.

DSL Auto-Regen was written and tested on Mudlet 4.19.1.

## Installation

Verify gmcp is enabled on your characters by typing the command `gmcp` in DSL if needed. To install the DSL Auto-Regen module, download [DSL-Auto-Regen.xml](DSL-Auto-Regen.xml) and in Mudlet go to Toolbox -> Module Manager -> Install to install the module.

## Configuration

Once the module has been installed, edit the configuration at the top of the module's script by clicking on "Scripts" in the Mudlet menu then clicking on the DSL-Auto-Regen -> DSl-Auto-Regen script. Add any Conclave characters that you wish to use the Auto-Regen module with by adding their names to the characterList. Additional configuration options can be added such as a list of characters to skip, the default option as to whether the module should be enabled or disabled when logging in, auto sleep functionality, and options to enable INFO and DEBUG statements among other configuration options.

## Usage

Once the module has been installed and configured, type `autoregen` if you wish to disable it as it is enabled by default. To force an Auto-Regen process to run while within the Conclave Common Room, you can type `autoregen run` which will look at the room to detect all individuals and begin the Auto-Regen process.

## Features

The Auto-Regen module offers the following features.

* Automatically adds Conclave members to the list of characters to regenerate as they enter the commons
* Automatically glances at characters to determine their overall health and automatically links to them
* Detects your character's mana to only cast the number of regenerations that current mana allows
* Casts only the number of regeneration spells that can be cast before the next tick and leaves a configurable buffer of seconds free for actions such as sleeping before the tick
* Disables any actions when your character is AFK
* Creates triggers and events as you enter the Commons and destroys them upon leaving, freeing up resources when not within the commons
* Ignores characters that have hit excellent health for a configurable cooldown time before attempting to regenerate them again
* Monitors affects using GMCP to determine if you are a ghost to disable Auto-Regen to prevent PK interference
* Hides the commands and spam related to linking to characters
* Can force the process to run while in the Commons by typing `autoregen run` which will clear out the current state of all characters and will look at the characters in the room to attempt to regenerate anyone that is in need of it 
* Casts regeneration a number of times based on the current health of characters
* Can set AUTO_SLEEP = true to allow automatically sleeping before the tick and awaking on the tick when your mana is not fully recovered
