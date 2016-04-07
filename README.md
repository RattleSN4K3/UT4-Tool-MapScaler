# UT4-Tool-MapScaler
Lets you scale your map

## Preview
![Preview](../gh-pages/resources/preview.gif)

## Key features:
 - Scale down/up an entire map
 - Scale only selected objects
 - Align irregular Actors to floor or keep them floating
 - Non-uniform scaling
 - Undo scaling on the fly
 - Store/restore selection
 - Work on any scaled level, changes will be updated to previous scales


## Installation:
 - Extract the archive
 - Move/copy "MapScaler.uasset" into the content folder of _Unreal Tournament_  
   `.\UnrealTournamentEditor\UnrealTournament\Content`  
   ('UnrealTournamentEditor' is the root of the editor installation and may differ)

## Usage:
 - Open your map
 - Place the _**MapScaler**_ actor into your map
 - Select the actor and set up `Scale Factor` to your desired scale
 - Click on `Scale` once in order to start the process

   **!!! Note**: Most of the checkboxes (like `Scale Level`, `Undo`, `Redo` etc.) won't be shown as ticked ever.

 - After the scaling process is done, which should be immediately, you can delete the actor
 - Keep in mind, that some lighting properties are also scaled. Always check the scaling properties


## Native support:

In order to fully scale every scale-able and noticeable properties of some actors, the _MapScaler_
has to use a native plugin. The engine does not support changing some properties from the Blueprint
context, thus the native plugin features some methods to changes these from the _MapScaler_ actor.

Only some light properties of static/stationary lights (including _SkyLights_, _DirectionalLights_, etc.)
will require the need of the native support. Depending on the configuration, the _MapScaler_ will state
whether a plugin is required or not in the "Native support" field/property in the details panel.

In order to active the native support, you only have to install the native plugin. Once installed,
the _MapScaler_ will print out the running version.

Note:
The native plugin is not interchangeable throughout engine versions / editor builds. Every time the
editor is updated, the _MapScaler_ plugin has to be updated.


## Configuration:

The _MapScaler_ has several different options to configure the scaling, what type of objects
are scaled, what properties should be scaled or simply check some data stats. You can find
these options in the details tab while having the _MapScaler_ selected.

Each time any property is changed, the _MapScaler_ will check the map, process some data and
stores it into the local storage. This is used for various features after having scaled a
map or undo the scaling. Due to this mechanism, changing various properties may take time
depending on the size / actor count of the map.

Check the [MapScaler_Readme.txt](MapScaler_Readme.txt) for more information.


## Author
RattleSN4K3


## Credits:

 - Neil Moore alias CaptainMigraine  
   Initial idea / requests for scaling his map DM-Lea to match some changes to the movement scale
