# Character Management

## Linking a Character Sheet
Linking a character sheet is needed for many of Avrae’s features. This will allow you to roll directly for things, and saves you the trouble of having to remember your modifiers. That way you can do things like: `!check arcana`, `!save dexterity`, `!attack longsword`

To link a D&D Beyond character to the bot:

```sh
!import https://ddb.ac/...
```

To update the bot's version of your character from your sheet (e.g. after a level-up)
```sh
!update
```

To show your character's current status (e.g. hit points, spell slots, etc,)
```sh
!game status
```

## Using Purchased Content from DNDBeyond:
To use purchased content (e.g. casting spells, reference feature text) with Avrae, you'll need to link your Discord account to your D&D Beyond account as a one-time thing. This can be done from your [account settings](https://www.dndbeyond.com/account) page.

## Checking which character is presently being used
You can always check which character is currently linked to Avrae, by running
```sh
!character
```

## Managing Multiple Characters
If you have multiple characters in this game or in others, you can set the default character for this server

```sh
!character server <character name>
```

Or for a particular channel

```sh
!character channel <character name>
```

## Resting and Recharging
Take a short or long rest:
```sh
!game shortrest
!game longrest
```

## Monitoring your character's conditions
In D&D, there are many different conditions which a character might experience, such as _"Blinded"_, _"Paralyzed"_, _"Stunned"_, ...

To keep track of your character's conditions, you can type:
```sh
!status
```

## Managing your character's health

To check your character's current health, you can type one of:
```sh
!game status
!g status
```

Any changes to your characters health will be mirrored in the linked D&D Beyond character sheet.


## Manually adjusting your character's health

There might be some situations in which you might need to manually adjust your character's health.

Adding/subtracting health points can be done using the following commands:

```sh
!game hp <add/subtract> digits
!g hp <add/subtract> digits
```

Examples:

```sh
# add 7 points to your character's overall health
!g hp + 7

# subtract 4 points from your character's overall health
!g hp - 4
```


## Manually Editing Spell Slots
Manually edit your character’s available spell slots:
```powershell
# Format: !game spellslot <slot level> <+/-><number of slots>
!game spellslot 5 +2
!g ss 5 +2
```

## Manually Editing Custom Counters
Manually edit your character’s available custom counters:
```powershell
# Format: !game customcounter <name> <+/-><number of slots>
!g cc luck -1
```

## Creating a counter
```powershell
!cc create "Healing Word (Enspelled Staff)" -min 0 -max 6 -type bubble -reset long -resetby 1d6 -value 6
```