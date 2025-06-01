# Class Specific Commands

## Barbarian
### Rage
You can enter rage as a Bonus Action using the following command:

```sh
!a "Rage"
```

This will apply all resistance effects and damage bonuses for the length of the effect (10 minutes). According to the rules, to extend your rage from round to round, you need to either make an attack, or use a Bonus Action to extend it. Avrae will not automatically end the effects, unless it is told to.

Your rage effect will be removed when combat ends. To end rage early, the DM can remove the effect with:

```sh
!i re <combatant name> Rage
```

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

## Monk
### Agile Perry
To use Agile Perry after an unrarmed strike (and you are holding a Kensei weapon), you can take the agile perry action

```sh
!a "Agile Perry"
```

You can also add it to the attack like this:

```sh
!a "Unarmed Strike" -t GO1 perry
```

### Deflect Attack
To deflect the damage from an attack use the Deflect Attack action to automatically roll the die and apply the HP back to your character.

```sh
!a "Deflect Attack"
```

If the damage is reduced to zero, you can expend a focus point to redirect the attack
```sh
!a "Deflect Attack: Redirect Attack" -t OA3
!cc "Focus Points" -1
```
Note: There is a bug in this action which requires you to deduct the focus point manually. Be sure you have a focus point available before you use the action. You can check your focus points with `!cc "Focus Points"`.

### Flurry of Blows
To properly deduct focus points, use the Flurry of Blows action first, followed by the additional unarmed strike.

```sh
!a "Flurry of Blows"
!a "Unarmed Strike: -t GO1
```
### Focused Patient Defense
Only use this action if you want to use the "focused" patient defense as it will deduct a focus point and add the dodge effect to your character. If you just want the normal patient defense, just use it for free as a disengage bonus action.

```sh
!a "Patient Defense"
```

### Step of the Wind
There are three options for this action, the last (dash and disengage) deducts a focus point.

```sh
!a "Step of the Wind (Dash)"
!a "Step of the Wind (Disengage)"
!a "Step of the Wind (Dash and Disengage)"
```

Alternatively, you can use:

```sh
!a step
```
Avrae will prompt you to choose one of the above actions.

### Uncanny Metabolism
When you roll initiative, you can also take the Uncanny Metabolism action, which will restore your focus points and some HP.

```sh
!init join
!move J13
!a "Uncanny Metabolism"
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

## Rogue
### Sneak Attack/Cunning Strike
On a successful attack, where sneak attack damage is appropriate, roll a separate die for the sneak attack damage.

```sh
!attack sneak -t GO1
```

If you want to apply cunning strike to your sneak attack, add an option to the sneak attack roll:

```sh
!attack sneak -t GO1 -choice poison
```

The options are `poison`, `trip`, `withdraw`

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

### Wild Magic
The Wild Magic Alias helps with wild magic surges both with and without Tides of Chaos.

If you are rolling to "try to surge" after casting a sorcerer spell you can use:
```sh
!wms roll
```

This will both roll for a surge (1d20) and on a 20 will roll on the Wild Magic Surge Table (1d100) and display the result.

If you are rolling because you used Tides of Chaos and then cast a sorcerer spell, you can use `!wms tide` to both roll on the Wild Magic Surge Table and update your Tides of Chaos counter. The series of rolls would like something like this:

```sh
!a tides                    ## Activates tides of Chaos and reduces the counter
!check persuasion adv       ## Some d20 roll with advantage
!cast "Some Sorcerer Spell" ## Cast a sorcerer spell
!wms tide                   ## Rolls on the WMS table automatically  and Resets the ToC counter.
```

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