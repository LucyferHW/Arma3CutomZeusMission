# Load Costum Loadouts

## Tutorial
### outside of the game
- create a file named `description.ext`
- paste into this file
```
respawn=3;
respawnDelay=2;
respawnOnStart=-1;
```
- save and close the file
- create a folder named `loadouts` in the project directory.
- go into `./loadouts/`
- create for each loadout a `role.sqf` file
- open the file
- paste into the file on the top this "`unit = _this select 0;`"
- save the files

### in the game
- open vanilla Arsenal
- make a loadout
- export the loadout
*now you have a long text in your system clipboard*

### outside of the game
- paste the exported text into the `role.sqf` file under the first segment
- remove this lines:
```
comment "[!] UNIT MUST BE LOCAL [!]";
if (!local this) exitWith {};
```
```
comment "Set identity";
[this,"WhiteHead_20","male11eng"] call BIS_fnc_setIdentity;
```
- replace all `this` to `unit` !Not the "_this"!
- save the file

### in the game
- place a soldier
- paste in the Init field `[this] execVM "loadouts\role.sqf";`
- save
