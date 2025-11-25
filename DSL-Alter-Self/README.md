# DSL Alter-Self

The DSL Alter-Self module allows Transmuters to keep the alter self affect on themselves automatically.

DSL Alter-Self was written and tested on Mudlet 4.19.1.

## Installation

Verify gmcp is enabled on your characters by typing the command `gmcp` in DSL if needed. To install the DSL Alter-Self module, download [DSL-Alter-Self.xml](DSL-Alter-Self.xml) and in Mudlet go to Toolbox -> Module Manager -> Install to install the module. If you wish to make updates to the script itself for updating any of the configuration options, be sure to click the "sync" checkbox in the module manager.

## Usage

Once the module has been installed, type `alterself <mob>` or `aself <mob>` to enable the alter self functionality with the desired mob. Typing `alterself` or `aself` will toggle the functionality on and off. `alterself debug` or `aself debug` can be used to turn on the debug mode.

## Features

The Alter-Self module offers the following features.

* Automatically detects if the current character is a Transmuter before enabling the module
* Keeps the alter self affect upon the Transmuter when enabled.
* On tick, checks to see if the affect is missing and recasts as needed
* Stops attempting to cast if 5 attempts fail
* Will not automatically refresh the affect if fighting was detected in the past 30 seconds
* Does not cast if the character does not have enough mana to cast the spell
* Does not cast if the character is AFK
