# Currency

## Dictionary
In D&D, there are different coins, each one possessing a different value:

| Coin Type        | Abbreviation | Value in Copper Pieces (CP) | Exchange Rate      |
|------------------|--------------|-----------------------------|-----------------------------------|
| Copper Piece     | CP           | 1                           | 1 CP                             |
| Silver Piece     | SP           | 10                          | 10 CP = 1 SP                     |
| Electrum Piece   | EP           | 50                          | 5 SP = 1 EP = 50 CP              |
| Gold Piece       | GP           | 100                         | 2 EP = 1 GP = 10 SP = 100 CP     |
| Platinum Piece   | PP           | 1,000                       | 10 GP = 1 PP = 100 SP = 1,000 CP |

## Monitoring your character's holdings
You can check your character's holdings by typing:
```sh
!game coins
!g coins
```

## Managing your character's holdings
There might be some situations in which you might need to manually adjust your character's holdings.

Adding/subtracting coins can be done using the following commands:

```sh
!g coins [<add/subtract><digits><abbreviation>]+
```

Examples:

```sh
# add 7 silver pieces to your character's coin purse
!g coins +7sp

# subtract 4 gold pieces from your character's coin purse
!g coins -4gp

# add 3 gold pieces, 12 silver pieces and 25 copper pieces to your character's coin purse
!g coins +3gp +12sp +25cp
```

