# Respawn with same Loadout

## outside of the game
### onPlayerKilled.sqf
- create a file named `onPlayerKilled.sqf`
- paste this `player setVariable["Saved_Loadout",getUnitLoadout player];`


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
