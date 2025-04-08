
# Combat

## Initiative
Once the DM starts the initiative tracker, players can the  use `!init` command.

### Joining Initiative
Add your character to the initiative order:
```sh
!init join
```

and then place yourself on the map (use the coordinate on the map):
```sh
!move G7
```
### Ending Your Turn
End your turn and advance to the next combatant:
```sh
!init next
```
Forgetting to end your turn is a common mistake you should try to avoid.

### Other Initiative Commands
List the current order:
```sh
!init list
```

## Attack Rolls
Attack rolls for both attack and damage at once. The format is:
```sh
!attack <weapon> [flags|arguments]
```

Here are a some examples of attack rolls. Note that if the weapon's name is more than one word, it needs to be in quotes.
```sh
!attack longsword -t GO1
!attack "unarmed strike" -t OR1
!a halberd -t MA1 adv
!a dagger -rr 2 -t GO1
```

Some attacks might offer variations, which can be picked with the use of `choice`:
```sh
!a "Sneak Attack" -t oR1 -choice trip
```

### Example Melee Turn
Move into position:
```sh
!move F7
```

Attack the goblin with your longsword:
```sh
!attack longsword -t GO1
```

End your turn
```sh
!init next
```

## Spellcasting
Like attacks, spellcasting rolls the atttack and teh damage at once in this format:

Attack rolls for both attack and damage at once. The format is:
```sh
!cast <spell> [flags|arguments]
```

Here are a some examples of spellcasting rolls. Note that if the spell's name is more than one word, it needs to be in quotes:

```sh
!cast fireball -t DR1
!cast "healing word" -t "Fitz"
```

You can have multiple targets in some spells
```sh
!cast "Burning Hands" -t GO1 -t GO2 -t GO3
```

Many spells can be cast at multiple levels. You can control the level with `-l`
```sh
!cast "Ray of Sicknesss" -t GO1 -l 2
```

An example of a proper command with a target and advantage.
```sh
!cast fireball -t GO1 adv
```

Some other common flags:

- `-i ` Ignores spell slots and spellbooks, e.g. casting as a ritual or item.
- `-rr` Roll multiple times, such as for a warlock's multiple Eldritch Blasts.
- `-choice` Some attacks or spells can offer variants, e.g. using "Sneak Attack" with the variant of Trip/Prone.
- `-with <int/wis/cha>` Uses a different skill base for DC/AB (will not account for extra bonuses)

### Example Spellcasting Turn
Move into position:
```sh
!move F7
```

Cast Burning Hands into a 15ft cone toward three goblins:
```sh
!cast "Burning Hands" -t GO1 -t GO2 -t GO3
```

Move away:
```sh
!move G10
```

End your turn
```sh
!init next
```

## Using Your Reaction
Opportunity attacks:
```c
// Format: !init aoo "attacker name" "attack name" -t "target name"
!init aoo "Mal" "greataxe" -t "Goblin 1"
```

Cast a spell as a reaction:
```sh
# Format: !init reactcast "caster name" "spell name" -t "target name"
!init reactcast "Cindel" "fireball" -t "GO1" -t "GO2" -t "GO3"
```

Roll a concentration check:
```sh
# -dc #          Set the DC for the check. Returns a simpler "Success!" or "Fail!" dialog.
# -t "target"    Specify who is making the check.
!conc -dc 15 -t "Mind Flayer"
```

Use a class/build specific reaction:
```sh
# -amt #         Amount of damage taken
!a uncanny dodge -amt 12
```
