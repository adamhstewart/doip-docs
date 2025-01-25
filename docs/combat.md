
# Combat

## Initiative
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

## Attack Rolls
Rolls for both attack and damage at once.
```powershell
# Format: !attack <weapon> [flags|arguments]
# If the weapon's name is more than one word, it needs to be in quotes.
!attack longsword
!attack "unarmed strike"
!a halberd

# Common flags
# -rr #              Roll multiple times, such as for Multiattack or Extra Attack.
!attack longsword -rr 2

# -t "combatant"     Targets the specified combatant. Avrae will roll against the target's AC, and
#                    if the attack hits, apply the damage to the target's current HP. Also tracks
#                    length of effects, e.g. "until the end of its next turn." Can be repeated for
#                    multiple targets of the same attack. Mostly used with Avrae's initiative
#                    tracker.

# Common arguments
# dis                Applies disadvantage to the roll.
# adv                Applies advantage to the roll.
```

An example of a proper command with a target and advantage.

```sh
!attack longsword -t GO1 adv
```

An example of a proper command where the weapon is two words.

```sh
!attack "unarmed strike" -t GO1
```

## Spellcasting
```powershell
# Format: !cast "spell"
# If the spell's name is more than one word, it needs to be in quotes.
!cast fireball
!cast "healing word"

# Common flags:
# -i           Ignores spell slots and spellbooks, e.g. casting as a ritual or item.

# -l #         Specifies the level to cast the spell at.

# -rr #        Roll multiple times, such as for a warlock's multiple Eldritch Blasts.

# -t "combatant"        Targets the specified combatant. Avrae will have the target make the saving
#                       throw, and if the attack hits, apply the damage to the target's current HP.
#                       Can be repeated for multiple targets of the same attack. Mostly used with
#                       Avrae's initiative tracker.

# -with <int/wis/cha>   Uses a different skill base for DC/AB (will not account for extra bonuses)
```

An example of a proper command with a target and advantage.

```sh
!cast fireball -t GO1 adv
```
An example of a proper command with multiple targets.
```sh
!cast "burning hands" -t GO1 -t GO2 -t GO3
```

## Using Your Reaction
Opportunity attacks:
```c
// Format: !init aoo "attacker name" "attack name" -t "target name"
!init aoo "Dundan Hammerfist" "greataxe" -t "Goblin 1"
```

Cast a spell as a reaction:
```sh
# Format: !init reactcast "caster name" "spell name" -t "target name"
!init reactcast "Dundan Hammerfist" "fireball" -t "Goblin 1" -t "Goblin 2" -t "Goblin 3"


Roll a concentration check:
```sh
!conc

# -dc #          Set the DC for the check. Returns a simpler "Success!" or "Fail!" dialog.
# -t "target"    Specify who is making the check.
!conc -dc 15 -t "Mind Flayer"
```