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

## Manually Editing Spell Slots
Manually edit your character’s available spell slots:
```powershell
# Format: !game spellslot <slot level> <+/-><number of slots>
!game spellslot 5 +2
!g ss 5 +2
```
