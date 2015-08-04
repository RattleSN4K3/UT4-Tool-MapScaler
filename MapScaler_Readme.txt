Map Scaler

This is a simple script to be used in the editor which allows to scale the current level.

Version: 1.2
Compatibility: Build 2637632 (7/29/2015)
Type: Blueprint
by RattleSN4K3


Installation:
 - Extract the archive
 - Move/copy "MapScaler.uasset" into the content folder of Unreal Tournament
   .\UnrealTournament\Content


Usage:
 - Open your map
 - Place the "MapScaler" actor into your map
 - Select the actor and set up "Update scale" to your desired scale
 - Click on "Update" once in order to start the process
   
   !!! Note: The "Update" checkbox won't be shown as ticked ever.

 - After the scaling process is done, which should be immediately, you can delete the actor



Changelog:

v1.2
- Added: Field for ignoring specific actor/object classes for scaling
- Added: Re-align pickup bases on floor
- Added: Re-align player starts on floor
- Added: Option for re-aligning pickup bases
- Added: Option for non-uniform scale
- Added: Option for scaling Jump pad properties
- Changed: Removed debug code
- Fixed: Minor issues (such as typos, code cleanup, etc.)

v1.1
- Added: Scale BSP
- Changed: Hide irrelevant categories

v1.0 - Initial release
- Scale actors (such as StaticMeshActor, SkeletalMeshActor, etc.)
