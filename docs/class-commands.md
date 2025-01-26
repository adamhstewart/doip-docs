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