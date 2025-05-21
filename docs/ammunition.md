# Ammunition Tracking
If your character uses a bow or some other weapon that uses ammunition, you can track your inventory with several snippets.


## Using the Snippet

- For arrows: Add `arrow` in the attack command
- For crossbow bolts: Add `bolt` in the attack command

Examples:

```sh
# Shoot an arrow at the Goblin
!a Longbow -t GO1 arrow

# Shoot two arrows at the Goblin
!a Longbow -t GO1 -rr 2 arrow arrow

# Shoot a crossbow bolt at the Goblin
!a Longbow -t GO1 bolt

```

You can also collect your arrows at the end of a battle (requires a minute of time, per DM discretion)

```sh
# Collect arrows after a battle
!collect
```

## Setup
Before using, you need to set up counters to track your inventory

```sh
# Setup counters for arrows
!cc create "Arrows"
!cc create "Used Arrows"
```
