# General Avrae Documentation

Avrae is a powerful tool for play-by-post games, but it can be a little daunting. This guid and the associated sub-pages should help a little with reference. In general, a certain set of commands will become important to your character, and in time you will learn those commands well.

## Basic Command Structure

All commands start with a `!` and are followed (with no space) by a command, which varies by the action you want to perform. Teh notation in this guide follows a format like this

```sh
!<command> <a required argument/flag> [an optional argument/flag]
```

Note:

- items in `<>` are required
- items in `[]` are optional
- any item that has multiple word need to be enclosed in `""`

For example, here's a simple dice roll:
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