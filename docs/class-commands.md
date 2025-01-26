# Class Specific Commands

## Fighter
### Second Wind
To use an instance of Second Wind:
```sh
!wind
```
### Arcane Shot
To use Arcane shot after a hit on GO1 with your bow:
```sh
!arcane bursting -t GO1
```

These are the full set of Arcane Shot command options.
```powershell
!arcane help - This message!
!arcane ? - Also this message!
!arcane banishing - performs a Banishing Arrow
!arcane beguiling - performs a Beguiling Arrow
!arcane bursting - performs a Bursting Arrow
!arcane enfeebling - performs an Enfeebling Arrow
!arcane grasping - performs a Grasping Arrow
!arcane piercing - performs a Piercing Arrow
!arcane seeking - performs a Seeking Arrow
!arcane shadow - performs a Shadow Arrow
-i - when added after the shot name will prevent the alias from expending a use of your Arcane Shot
-t <target> - behaves the same as if you were targeting with your bow
```

## Druid

### Wild Shape

To turn into a beast during combat use  `!wildshape <creature name>`. For example to turn into a wolf:
```sh
!wildshape wolf
```

## Sorcerer
### Innate Sorcery
As a bonus action when you unleash the simmering magic within you, use the following command:
```sh
!a "Innate Sorcery"
```
This will apply the +1 DC bonus to your spell casting for 1 minute. It will NOT add the advantage. You should do that manually with tha `adv` argument, for example:
```sh
!cast "Dissonant Whispers" -t GO1 adv
```

This would target Goblin 1 with the Dissonant Whispers spell. A +1 DC bonus would be applied along with advantage on the d20 roll.

### Font of Magic
#### Convert a Spell Slot to Sorcery Points
You can expend a spell slot to gain a number of Sorcery Points equal to the slot’s level
```sh
!a "Font of Magic: Convert Spell Slots" -l 2
```
This will convert 1 level 2 spell slot to 2 sorcery points.

#### Convert Sorcery Points to Spell Slots
You can transform 2 unexpended Sorcery Points into a level 1 spell slot, which vanishes when you finish a Long Rest. As you increase in levels you can create more spell slots as described in the table.
```sh
!a "Font of Magic: Create Spell Slot"
```
This will convert 2 sorcery points to a level 1 spell (per the table).

#### Metamagic
These commands will just use the sorcery point, it doesn't have any impact on the casting.
```sh
!a "Metamagic: Distant Spell"
!a "Metamagic: Extend Spell"
```

In order to actually extend the duration on a spell, you need to add a flag on the cast command:
```sh
!cast "Calm Emotions" -t GO1 -dur 20
```
This would cast the Calm Emotions spell on Goblin 1 and would add the effect for 20 rounds (2 minutes).