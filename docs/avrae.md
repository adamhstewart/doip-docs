# General Avrae Documentation

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

## Flags and Arguments
Most Avrae commands have additional features that can be unlocked with the use of flags and arguments.

**Flags** (sometimes called **switches**) come after basic form of the command, and follow a set format

Here are some common flags:

```sh
# -t Targets a combatant.
!attack shortsword -t GO1       ## Targets Goblin 1

# -rr performs the action multiple times.
 !attack shortsword -t GO1 -rr 2       ## Makes two shortsword attacks on Goblin 1
```
Commonly used flags for commands are be listed under that command's documentation.

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