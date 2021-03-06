**Some commands have been temporarily ommited from this repository as I'm going through a complete refactorization and recode of this project before pushing the new changes.**

# TaeJa Bot
TaeJa Bot is a Discord Bot for Starcraft II clans. It runs on the <a href='https://github.com/vsTerminus/Mojo-Discord'>Mojo::Discord</a> library. 

TaeJa Bot can help manage your clan or simply for viewing player statistics.


## Command List & Options
**Example command outputs are shown further below**

`help`
- ~help
- ~help \<other command name\>

`player`
- ~player \<username\>
- ~player \<username\>[#sctag]
- ~player \<username\> [bronze|silver|gold|platinum|diamond|master|grandmaster]
- ~player \<username\> [terran|zerg|protoss|random]
- ~player \<username\> [us|kr|eu]
- ~player \<username\> [1..#]

`bnet`
- ~bnet \<username\>
- ~bnet \<username\>[#btag]
- ~bnet \<username\> [bronze|silver|gold|platinum|diamond|master|grandmaster]
- ~bnet \<username\> [terran|zerg|protoss|random]
- ~bnet \<username\> [us|kr|eu]
- ~bnet \<username\> [1..#]

`clan`
- ~clan \<name\>
- ~clan \<name\> [count <league|race>]
- ~clan \<name\> [terran|zerg|protoss|random]
- ~clan \<name\> [bronze|silver|gold|platinum|diamond|master|grandmaster]
- ~clan \<name\> [us|kr|eu]
- ~clan \<name\> <export>

`bounds`
- ~bounds \<na|kr|eu\>

## Command Explanations
`~help`
- Displays all available bot commands, if the command is followed by another command name, it'll give a detailed help page for the said command. i.e `~help player` will display a detailed help page for that command & its available options.

`~player`
- Given a \<username\> it'll display a list of all users with a similar name. Aditional parameters can be given to narrow down your search. 
- i.e. if you don't know their exact name, but know they are a "diamond" "zerg" in the "us" server, you can use the command: `~player part_of_name diamond zerg us`.

`~bnet`
The same explanation applies for ~bnet. Except that ~bnet searches for people by their Blizzard/Battle.net name rather than their in-game Starcraft name.

## How It Works
============

Rather than querying Blizzard's API everytime the bot is used, an hourly job executes a script to update a local database which is where the bot collects its data from.

With this system, the bot can provide more generalized and insightful view on data that would otherwise be near-impossible to classify from a straightup query of Blizzards API.

Categorization and querying of Clan Tags, Player Names, Player Battle Tags are not possible with Blizzard's API alone.
