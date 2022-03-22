# Respawn with first spawn loadout

## in the game
### for each Playableunit
- create a soldier
- paste this in the "Init" field: `this setVariable["Saved_Loadout",getUnitLoadout this];`

## outside of the game
### onPlayerRespawn.sqf
- create a file named `onPlayerRespawn.sqf`
- paste this:
```
removeAllWeapons player;
removeGoggles player;
removeHeadgear player;
removeVest player;
removeUniform player;
removeAllAssignedItems player;
clearAllItemsFromBackpack player;
removeBackpack player;
player setUnitLoadout(player getVariable["Saved_Loadout",[]]);
```


### description.ext
- create a file named `description.ext`
- paste this:
```
respawn=3;
respawnDelay=2;
respawnOnStart=-1;
```
