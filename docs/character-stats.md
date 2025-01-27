# Character stats in-game monitoring and management

## Checking which character is presently being used
You can always check which character is currently linked to Avrae, by running
```sh
!character
```

If the linked character does not meet your expectations, head over to [Character > Managing Multiple Characters](character.md#managing-multiple-characters)


## Monitoring your character's conditions
In D&D, there are many different conditions which a character might experience, such as _"Blinded"_, _"Paralyzed"_, _"Stunned"_, ...

To keep track of your character's conditions, you can type:
```sh
!status
```


## Managing your character's health

To check your character's current health, you can type one-of:
```sh
!game status
!g status
```

Any changes to your characters health will be mirrored in the linked D&D Beyond character sheet (more on this at [Character > Linking a Character Sheet](character.md#linking-a-character-sheet))


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

