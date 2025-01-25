# Player Reference
Roll some dice:
```sh
# Format: !roll <dice>
!roll 1d12+3
!r 1d12+2
```

Add advantage/disadvantage to a roll:
```sh
# adv       Roll with advantage.
!attack longsword adv
!check perception adv

# dis       Roll with disadvantage.
!save wisdom dis
!check arcana dis
```

### Linking a Character Sheet
Linking a character sheet is needed for many of Avrae’s features. This will allow you to roll directly for things, and saves you the trouble of having to remember your modifiers: `!check arcana`, `!save dexterity`, `!attack longsword`

To link a D&D Beyond character to the bot:

```sh
!beyond https://ddb.ac/...
```

To update the bot's version of your character from your sheet (e.g. after a level-up)
```sh
!beyond update
```

**Using Purchased Content:** To use purchased content (e.g. casting spells, reference feature text) with Avrae, you'll need to link your Discord account to your D&D Beyond account as a one-time thing. This can be done from your [account settings](https://www.dndbeyond.com/account) page.

## Flags and Arguments
Most Avrae commands have additional features that can be unlocked with the use of flags and arguments.

**Flags** (sometimes called **switches**) come after basic form of the command, and follow a set format, such as `-rr 3` and `-t Goblin`. Flags are specific to their command.

Commonly used flags for commands will be listed under that command's tutorial block.

**Arguments** go at the very end of a command, are usually a few letters long, and are mostly universal.

Here are some common arguments:
```sh
# adv       Roll with advantage.
!attack longsword adv
!check perception adv

# dis       Roll with disadvantage.
!save wisdom dis
!check arcana dis
```

To learn about all of the available options for a command, run `!help [command]`.

## Basic Character Commands
### Ability Checks
```sh
# Format: !check <skill/ability/"initiative">
!check arcana
!check wisdom
!check initiative  # Rolls for initiative
!c perc
```

### Saving Throws
```sh
# Format: !save <ability/"death">
!save wisdom
!save death        # Rolls a death save.
!s dex

# To reset Avrae's death save counters manually (automatically done when you heal HP):
!game deathsave reset
```

### Attack Rolls
Rolls for both attack and damage at once.
```powershell
# Format: !attack "weapon"
# If the weapon's name is more than one word, it needs to be in quotes.
!attack longsword
!attack "unarmed strike"
!a halberd

# -rr #              Roll multiple times, such as for Multiattack or Extra Attack.
!attack longsword -rr 2

# -ac #              Specify an AC to hit against. Only rolls for damage on hit.
!attack longsword -ac 14

# -t "combatant"     Targets the specified combatant. Avrae will roll against the target's AC, and
#                    if the attack hits, apply the damage to the target's current HP. Also tracks
#                    length of effects, e.g. "until the end of its next turn." Can be repeated for
#                    multiple targets of the same attack. Mostly used with Avrae's initiative
#                    tracker.
!init attack longsword -t "Goblin 1"
```

### Spellcasting
```powershell
# Format: !cast "spell"
# If the spell's name is more than one word, it needs to be in quotes.
!cast fireball
!cast "healing word"

# -i           Ignores spell slots and spellbooks, e.g. casting as a ritual or item.
!cast wish -i
# -l #         Specifies the level to cast the spell at.
!cast fireball -l 9

# -rr #        Roll multiple times, such as for a warlock's multiple Eldritch Blasts.
!cast "eldritch blast" -rr 3

# -t "combatant"        Targets the specified combatant. Avrae will have the target make the saving
#                       throw, and if the attack hits, apply the damage to the target's current HP.
#                       Can be repeated for multiple targets of the same attack. Mostly used with
#                       Avrae's initiative tracker.
!init cast fireball -t "Goblin 1" -t "Goblin 2" -t "Goblin 3" -t "Goblin 4"

# -with <int/wis/cha>   Uses a different skill base for DC/AB (will not account for extra bonuses)
!cast "burning hands" -with cha
```

## Resting and Recharging
Take a short or long rest:
```sh
!game shortrest
!game longrest
```

Manually edit your character’s available spell slots:
```powershell
# Format: !game spellslot <slot level> <+/-><number of slots>
!game spellslot 5 +2
!g ss 5 +2
```

## Initiative and Combat
Once the DM starts the initiative tracker, players can the  `!init` command.

Add your character to the initiative order:
```sh
!init join
```

End your turn and advance to the next combatant:
```sh
!init next
```

List the current order:
```sh
!init list
```

### Attacking and Casting
On your turn, you can use special attack and cast commands. They work largely like `!attack` and `!cast`, but the `-t` flag can now be used to target other combatants in initiative, and works with the built-in HP tracking.

```powershell
# Format: !init attack "attack name" -t "target"
!init attack "longsword +1" -t "Goblin 1" -rr 2

# Format: !init cast "spell name" -t "target"
!init cast "fireball" -t "Goblin 1" -t "Goblin 2" -t "Goblin 3"
```

### Other Actions
Grapple a target or escape a grapple:
```sh
!grapple -t "target"
!escape
```

Shove someone:
```sh
!shove -t "target"
```

Roll a concentration check:
```sh
!conc

# -dc #          Set the DC for the check. Returns a simpler "Success!" or "Fail!" dialog.
# -t "target"    Specify who is making the check.
!conc -dc 15 -t "Mind Flayer"
```

### Using Your Reaction
Opportunity attacks:
```c
// Format: !init aoo "attacker name" "attack name" -t "target name"
!init aoo "Dundan Hammerfist" "greataxe" -t "Goblin 1"
```

Cast a spell as a reaction:
```sh
# Format: !init reactcast "caster name" "spell name" -t "target name"
!init reactcast "Dundan Hammerfist" "fireball" -t "Goblin 1" -t "Goblin 2" -t "Goblin 3"