# Custom Actions
Sometimes you want to add a custom action to your character. You can do so with the `!a import` command or in the <a href="https://avrae.io/dashboard/characters" target="_blank">Avrae dashboard</a>.


## Adding a Custom Action

You can add an action by running:

`!a import <paste custom action yaml code here>`

Or on your Avrae dashboard, you can add an action by following these steps:

1. Go to Hover over your character and click on the tool icon to "Edit Action."
2. To import one of the actions from below, click on the "Import YML" icon; otherwise, click "New..." to build your own action.
3. Paste the custom yaml code (options below) into the space provided and click "Import."
4. Click Save and Exit.

Your custom action should be usable by running `!a "Action Name"` in Discord.


## Sample Custom Actions
These actions are built for character use as needed. Use the steps above to add any of these actions to your character.

### Fire's Burn
```yaml
name: Fire's Burn
automation:
  - type: target
    target: all
    effects:
      - type: damage
        damage: 1d10[fire]
        overheal: false
  - type: counter
    counter: Fire's Burn (Fire Giant)
    amount: "1"
    allowOverflow: false
    errorBehaviour: warn
_v: 2
proper: true
verb: adds damage with
phrase: When you hit a target with an attack roll and deal damage to it, you can
  also deal 1d10 Fire damage to that target.
```
### Healing Word (Enspelled Staff)
```yaml
name: Healing Word (Enspelled Staff)
automation:
  - type: spell
    id: 2619143
    level: 1
    dc: "13"
    attackBonus: "5"
    castingMod: null
    parent: null
  - type: counter
    counter: Healing Word (Enspelled Staff)
    amount: "1"
    allowOverflow: false
    errorBehaviour: raise
_v: 2
proper: true
verb: uses
```

### Blade Word (Enspelled Armor)
```yaml
_v: 2
name: Blade Ward (Enspelled Armor)
automation:
  - type: spell
    id: 2618931
    level: 1
    dc: "13"
    attackBonus: "5"
  - type: counter
    counter: Blade Ward (Enspelled Armor)
    amount: "1"
    allowOverflow: false
    errorBehaviour: raise
verb: uses
proper: true
```

### Throwing Oil at a Creature
```yaml
name: Oil (Douse Creature)
automation:
  - type: target
    target: all
    effects:
      - type: save
        stat: dex
        fail:
          - type: ieffect2
            name: Covered in Oil
            duration: "10"
            effects: null
            attacks: []
            buttons: []
            end: false
            conc: false
            desc: If the target takes Fire damage before the oil dries (after 1 minute), the
              target takes an extra 5 Fire damage from burning oil.
            stacking: false
            save_as: null
            parent: null
            target_self: false
            tick_on_caster: false
        success: []
        dc: 8 + proficiencyBonus + dexterityMod
      - type: text
        text: When you take the Attack action, you can replace one of your attacks with
          throwing an Oil flask. Target one creature or object within 20 feet of
          yourself. The target must succeed on a Dexterity saving throw (DC 8
          plus your Dexterity modifier and Proficiency Bonus) or be covered in
          oil. If the target takes Fire damage before the oil dries (after 1
          minute), the target takes an extra 5 Fire damage from burning oil.
        title: Dousing a Creature or an Object
_v: 2
activation_type: 1
```
