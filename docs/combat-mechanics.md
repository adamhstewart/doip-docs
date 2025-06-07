# Combat Mechanics
These are house rules for this guild based that are either different then 2024 5e rules as written or are further clarifications of existing rules.

## Administering Healing Potions
Healing potions can be administered as a bonus action to yourself or another character within your reach (generally 5ft).

Healing potions can be administered to a character in any state of consciousness. The PC administering the potion must be conscious.

## Diagonal Movement
All character movement follows the "5-10-5" rules (5ft for the first square, then 10ft for the next square, then 5ft, then 10ft and so on).

The `!distance` alias can give an accurate assessment of the distance between spaces on a map and can be used to plan movement.

```sh
!distance a1 b13
```

## Help Action
In order to provide help, you must have an proficiency in the skill with which with you are helping. If there is no particular skill, it is a DM discretion.

The help action as a distraction for advantage on attacks can be performed by any character within 5ft of the target. This serves as the "flanking" rule in that advantage can only be granted when an action is used to give it, not simply by virtue of being within 5ft of the target. The most common use of this action is by familiars/summoned.

## Shields
Donning a shield is a free interaction that can be taken only at the start of your turn. If you use a 2-handed weapons to attack on your turn, your shield is doffed until the beginning of your next turn, unless you use your bonus action to don it.

If you don’t use the 2-handed weapon on your next turn, it’s automatically donned. No need to use an action or BA to don it.

If you use a 2-handed weapon and you don't intend to use your bonus action to don it, you can use the `doff` snippet as part of your attack roll. If you forget, either the player or the DM can use the `!doff` alias after the attack to have the same effect.

If you have a shield, you should set up your AC bonus by running `!cvar shieldValue 3` where the number is the AC Bonus you get for your particular shield.

## Surprise Attacks
In cases where surprise is established - generally through hidden/invisible condition for the party - the attacking party gets a full round of turns in initiative order. This surprise round counts as a full round for durations of effects, spells, etc. After each character has taken their turn, combat proceeds at the top of the initiative order.

Full party invisibility/hidden condition can be achieved as a group when over half of the party succeeds on a stealth check or the DM otherwise determines they are hidden or invisible.

## Firearms
No firearms.