# Species Specific Commands

## Aasimar
### Celestial Revelations
These traits can be partially controlled by the `!celestial <type>` alias which takes `heavenly`, `necrotic` or `raidiant` as arguments. For example

```sh
!celestial heavenly
```

Will activate the Heavenly Wings version of Celestial Revelations. It does two things:

1. It adds +2 radiant damage to all successful attacks
2. It adds the "Celestial Revelations" condition to the character in initiative with the duration tracked, along with a note about the ability (in this case, that the character can fly)

For **Necrotic Shroud**, the initiative note gives the DC Save number for combatants in range, but does not roll the save or apply the condition - that should be done manually.

For **Inner Radiance**, the initiative note gives the damage information, but dies not roll the attack or apply the damage - that should be done manually.

### Healing Hands
To use healing hands:
```sh
!a "Healing Hands" -t "Mal"
```
This would add the appropriate number of HP to Mal.