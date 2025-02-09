# Class Specific Commands

## Cleric

### Channel Divinity
You can channel energy directly from the Outer Planes to fuel magical effects. When you use this class’s Channel Divinity, you can choose which effect to create. You can use this class’s Channel Divinity 2 times per Long Rest, but can regain one expended use after finishing a Short Rest.

The options of this spell can be used as follows:
```sh
!a "Channel Divinity: Divine Spark (Heal)" -t Fitz
!a "Channel Divinity: Divine Spark (Damage)" -t GO1
!a "Channel Divinity: Preserve Life" -t Oak
!a "Channel Divinity: Turn Undead" -t ZO1 -t ZO2
```

Alternatively, you can shortcut in this way:
The options of this spell can be used as follows:
```sh
!a "Channel Divinity" -t Fitz
```

and Avrae will prompt you to choose which Channel Divinity spell to use. In either case, Avrae will update the counter of your Channel Divinity uses.

### Magic Initiate Spells
In order to use your Magic Initiate spells, there's a small hack to get it to work initially. As a one-time setup, run:
```sh
!ccspellimport
```

After that, you can use:
```sh
!a "Bless" -t Fitz
```

and it will use your Magic Initiate counter rather than your spell slot. This is only relevant for leveled spells, cantrips can be cast normally since they don't use spell slots.

### Life Domain Cleric
When a spell you cast with a spell slot restores HP to a creature, that creature regains an additional 2 + the spell slot’s level. To utilize this trait, use teh following:

```sh
!lifecast "Cure Wounds" -l 2 -t Cailen
```

This will provide the appropriate bonus to your spell according to the level cast (in this case, level 2).

## Druid

### Wild Shape
To turn into a beast during combat use  `!wildshape <creature name>`. For example to turn into a wolf:
```sh
!wildshape wolf
```

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

## Ranger
### Hunter's Mark
To track the uses and set the "Marked" effect on the combatant `!cast "Hunter's mark" -t GO1`

To add damage, use "mark" in the attack on your marked combatant. For example, `!attack longbow mark -t GO1` attacks GO1 and adds the Hunter's Mark damage automatically.

*Unfortunately, this automation requires the player to remember which combatant is "marked" and to apply the "mark" snippet to the command manually.*

A typical turn, applying and using Hunter's Mark would go like this. First, use the bonus action to apply Hunter's Mark to Goblin #1.

```sh
!cast "Hunter's Mark" -t GO1
```

Next, attack the Goblin with your longbow, applying the Hunter's Mark extra damage (if you hit).
```sh
!attack Longbow -t GO1 mark
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

## Warlock
### Hex
To track the uses and set the "Hex" effect on the combatant `!cast "Hex" -t GO1`

To add damage, use "hex" in the attack on your hexed combatant. For example, `!cast "Eldritch Blast" -t GO1 hex` attacks GO1 and adds the Hex damage automatically.

*Unfortunately, this automation requires the player to remember which combatant is "marked" and to apply the "mark" snippet to the command manually. It also cannot automatically apply disadvantage to an ability check, so that aspect of teh spell should be declared when using it.*

A typical turn, applying and using Hex would go like this. First, use the bonus action to apply HHex to Goblin #1.

```sh
!cast "Hex" -t GO1

And I am also Hexing his strength ability.
```

Next, cast Eldritch Blast on the Goblin, applying the Hex's extra damage (if you hit).
```sh
!cast "Eldritch Blast" -t GO1 hex
```