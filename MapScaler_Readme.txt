Map Scaler

This is a simple script to be used in the editor which allows to scale the current level.

Version: 1.4
Compatibility: built on Build 2926870 (3/31/2016)
Game: UT Pre-Alpha (UE4)
Type: Blueprint

Coded by RattleSN4K3
Credits: Epic Games


Key features:
--------------------------------
 - Scale down/up an entire map
 - Scale only selected objects
 - Align irregular Actors to floor or keep them floating
 - Non-uniform scaling
 - Undo scaling on the fly
 - Store/restore selection
 - Work on any scaled level, changes will be updated to previous scales


Installation:
--------------------------------
 - Extract the archive
 - Move/copy "MapScaler.uasset" into the content folder of Unreal Tournament
   .\UnrealTournamentEditor\UnrealTournament\Content

   ('UnrealTournamentEditor' is the root of the editor installation and may differ)


Usage:
--------------------------------
 - Open your map
 - Place the "MapScaler" actor into your map
 - Select the actor and set up "Scale factor" to your desired scale
 - Click on "Scale Level" once in order to start the process
   
   !!! Note: Most of the action checkboxes (like "Scale Level", "Undo", etc.) won't be shown as ticked ever.

 - After the scaling process is done, which should be immediately, you can delete the actor
 - Keep in mind, that some lighting properties are also scaled. Always check the scaling properties



Native support:
--------------------------------
In order to fully scale every scale-able and noticeable properties of some actors, the MapScaler
has to use a native plugin. The engine does not support changing some properties from the Blueprint
context, thus the native plugin features some methods to changes these from the MapScaler actor.

Only some light properties of static/stationary lights (including SkyLights, DirectionalLights, etc.)
will require the need of the native support. Depending on the configuration, the MapScaler will state
whether a plugin is required or not in the "Native support" field/property in the details panel.

In order to active the native support, you only have to install the native plugin. Once installed,
the MapScaler will print out the running version.

Note:
The native plugin is not interchangeable throughout engine versions / editor builds. Everytime the
editor is updated, the MapScaler plugin has to be updated.



Configuration:
--------------------------------

The MapScaler has several different options to configure the scaling, what type of objects
are scaled, what properties should be scaled or simply check some data stats. You can find
these options in the details tab while having the MapScaler selected.

Each time any property is changed, the MapScaler will check the map, process some data and 
stores it into the local storage. This is used for various features after having scaled a
map or undo the scaling. Due to this mechanism, changing various properties may take time
depending on the size / actor count of the map.

The following list will explain the options you can change from the details tab. Most of 
them are self explantory.


Section: MapScaler
] the main properties/actions

:: Scale level (Action)
   Applies the scale to every level object with the given value of "Scale factor"

:: Scale Selected Actors (Action)
   Applies the scale to selected objects with the given value of "Scale factor"

:: Undo (Action)
   Un-do the last scaling process

:: Revert (Action)
   Revert scalings back to its original values. Requires that undo data is present and not cleared.

:: Store Selection (Action)
   Stores the current selection of actors

:: Restore Selection (Action)
   Restores the stored selection of actors

- Error
  Info about the last occurred error

- Scale Factor
  The scale to apply to each level actor/BSP.

- Native Support
  Info about native plugin


Section: Scaling Options
] main options to specify what type of actors to scale, select pivot, or choose to align pickups

- Auto Align Pickups		(Default: True)
  Whether pickup bases should be aligned to the floor during scaling
  
- Override Scale Z	(Default: True)
  Whether to use a custom scale factor for Z

- Scale Z = <number>		(Default: 1.0)
  Scale factor for Z if 'Override Scale Z' is set

- Scale JumpPad		(Default: True)
  Whether to adjust the jump distance for Jump pads

- Scale Matinee		(Default: True)
  Whether to adjust the matinee data

- Scale Lights		(Default: True)
  Whether to adjust the properties of Lights (PointLight, DirectionalLight, etc.)

- Scale SkyLights		(Default: True)
  Whether to adjust the properties of SkyLights

- Scale Fog		(Default: True)
  Whether to adjust the fog (radii, distances, falloffs, etc.)

- Selection Pivot Scaler		(Default: False)
  Whether the MapScaler should be the pivot for scaling the selected actors only

- Override Pivot		(Default: False)
  Whether to use a pivot location for scaling actors accordingly related to that location

- Pivot	= <Actor>	(Default: )
  The custom actor for the pivot

- Override Use PivotBounding		(Default: False)
  Whether to use the bounding of the Pivot actor in the directon of 'PivotBoundingDirection'

- Pivot Bounding Direction = {X|Y|Z|-X|-Y|-Z}		(Default: -Z)
  The direction to calculate the Pivot's bounding

- Update Undo For NewActors		(Default: True)
  Whether to check for new actors and include them in the undo history

- Update Undo For Changes		(Default: True)
  Whether to check for changes and update undo data


Section: Scaling Properties
] options for specific properties of scale-able ACtors to choose specifically if it should be scaled or not

- Scale JumpPad Distance		(Default: True)
  Whether to adjust the jump distance for Jump pads

- Scale JumpPad Time		(Default: True)
  Whether to adjust the jump time for Jump pads

- Scale JumpPad RestrictedTime		(Default: True)
  Whether to adjust the restricted time for Jump pads


- Scale Light Component Intensity		(Default: False)
  Whether to scale the LightComponent property Intensity

- Scale Light Component IndirectLightingIntensity		(Default: False)
  Whether to scale the LightComponent property 'Indirect Lighting Intensity'

- Scale Light Component LightFunction Scale		(Default: False)
  Whether to scale the LightComponent property 'LightFunctionScale'

- Scale Light Component LightFunction FadeDistance		(Default: False)
  Whether to scale the LightComponent property 'Light Function Fade Distance'


- Scale PointLight Component AttenuationRadius		(Default: True)
  Whether to scale the PointLightComponent property 'AttenuationRadius'

- Scale PointLight Component SourceRadius		(Default: True)
  Whether to scale the PointLightComponent property 'SourceRadius'

- Scale PointLight Component SourceLength		(Default: True)
  Whether to scale the PointLightComponent property 'SourceLength'

- Scale PointLight Component LightFalloffExponent		(Default: False)
  Whether to scale the PointLightComponent property 'LightFalloffExponent'


- Scale DirectionalLight Component OcclusionDepthRange		(Default: False)
  Whether to scale the DirectionalLightComponent property 'OcclusionDepthRange'

- Scale DirectionalLight Component DynamicShadowDistanceMovableLight		(Default: False)
  Whether to scale the DirectionalLightComponent property 'DynamicShadowDistanceMovableLight'

- Scale DirectionalLight Component DynamicShadowDistanceStationaryLight		(Default: False)
  Whether to scale the DirectionalLightComponent property 'DynamicShadowDistanceStationaryLight'

- Scale DirectionalLight Component FarShadowDistance		(Default: False)
  Whether to scale the DirectionalLightComponent property 'FarShadowDistance'

- Scale DirectionalLight Component DistanceFieldShadowDistance		(Default: False)
  Whether to scale the DirectionalLightComponent property 'DynamicShadowDistanceStationaryLight'


- Scale SkyLightComponent SkyDistanceThreshold		(Default: True)
  Whether to scale the SkyLightComponent property 'SkyDistanceThreshold'

- Scale SkyLightComponent OcclusionMaxDistance		(Default: False)
  Whether to scale the SkyLightComponent property 'OcclusionMaxDistance'

- Scale SkyLightComponent MinOcclusion		(Default: False)
  Whether to scale the SkyLightComponent property 'MinOcclusion'


- Scale ExponentialHeightFog Component FogStartDistance		(Default: True)
  Whether to scale the ExponentialHeighFogComponent property 'Start Distance'

- Scale ExponentialHeightFog Component DirectionalInscatteringStartDistance		(Default: True)
  Whether to scale the ExponentialHeighFogComponent property 'Directional Inscattering Start Distance'

- Scale ExponentialHeightFog Component FogHeightFalloff		(Default: True)
  Whether to scale the ExponentialHeighFogComponent property 'Start Distance'


- Scale AtmosphericFog Component StartDistance		(Default: True)
  Whether to scale the AtmosphericFogComponent property 'Start Distance'

- Scale AtmosphericFog Component DistanceOffset		(Default: True)
  Whether to scale the AtmosphericFogComponent property 'Distance Offset'

- Scale AtmosphericFog Component DistanceScale		(Default: True)
  Whether to scale the AtmosphericFogComponent property 'Distance Scale'

- Scale AtmosphericFog Component AltitudeScale		(Default: True)
  Whether to scale the AtmosphericFogComponent property 'Altitude Scale'

- Scale AtmosphericFog Component GroundOffset		(Default: True)
  Whether to scale the AtmosphericFogComponent property 'Ground Offset'


Section: Scaling Selection
] various fields to specify what type of Actor to ignore for scaling, aligning, etc.

- Ignore BSPs = <Array of Actor Components>
  List of Object types to ignore scaling (for BSP scaling)
  Default value:
   > StaticMeshComponent
   > SkeletalMeshComponent

- Align Actors = <Array of Actors>
  List of Actor classes to align to floor
  Default value:
   > PlayerStart
   > UTPickup
   > UTPickupToken

- Ignore Actors Scale = <Array of Actors>
  List of Actor classes to ignore scaling
  Default value:
   > PlayerStart
   > UTPickup
   > UTPickupToken
   > UTJumpPad
   > CameraActor

- Align Floating Actors = <Array of Actors>
  List of Actor classes to ignore attempting to align if floor cannot be trace-checked.
  Default value:
   > PlayerStart
   > UTPickupToken
   > CameraActor


Section: Data / Info
] general info about the map / MapScaler

- Print Debug		(Default: True)
  Whether to print out debug messages into the output log

- Undo Count = <number>
  Amount of undo steps

- Undo Data = <text>
  Approx. size of scaling cache

- Clear Undo (Action)
  Check to clear undo data (the scaling cannot be reverted afterwards)

- Stored Selection = <text>
  Info about the stored actors

- Level Bounding = <text>
  The max and min bounding for this level.

- Level Size = <text>
  The square size of the level and also the full size (volume)

- TotalScale = <text>
  The resulting scale taking every scale into account

- ErrorProperties = <Array of String>
  Prints out problems with accessing properties



Changelog:
--------------------------------
v1.4
- Added: Optional native backend
- Added: Matinee sequences scaling (movement track)
- Added: Light properties scaling (e.g. Directional, Point, Sky)
- Added: Fog properties scaling (Exponential, Atmospheric)
- Added: Undo data updates for new actors
- Added: Option to scale selected objects only
- Added: Option to choose custom pivot (for scaling)
- Added: Option to store and restore selection actors
- Added: Map info in data section
- Added: Ignoring additional actors when scaling (Pickup token, Camera actors)
- Added: Info about resulting scale if multiple scaling processes were done
- ADded: Properly revert scaling for mixed undo data (all/selected)
- Added: Option to use pivot's bounding instead of center
- Removed: Component scaling not used anymore
- Changed: Transform selection restored (for proper grid)
- Changed: Proper data size calculation
- Changed: Proper tooltips for various properties
- Changed: Minor changes to clean up code
- Fixed: Crash for scaling with a factor of 0.0
- Optimized: Aligning of pickup classes (and tokens)
- Optimized: Dropping actors' initialization
- Optimized: Iteration of undo data
- Optimized: Snapshot data check

Native support:
- Added: Notifications
- Added: Extended light properties scaling
- Added: Version info

Experimental:
- Added: Mirror mode


v1.3
- Added: Undo system
- Added: Option to turn off debug messages in output log
- Changed: Renamed "Update" to "Scale"


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



Issues:
--------------------------------
- Maps with many actors (5000 and up) and many undo steps may crash the script which will result 
  into a unfinished and broken scaling process. The MapScaler is optimized to not crash for such 
  large maps but it can happen. The first/only scaling process will likely always run and finish 
  successfully. In case you encountered problems, try to untick "Update Undo For NewActors" and 
  "Update Undo For Changes" which will speed up the algorithm / execution loop.

- Using the native plugin can ocassionally result into being unloaded when you edit and compile
  the MapScaler Blueprint. The "Native support" field will likely state that the plugin is required.
  Simply re-open the map or type in the console command "MapScaler Fix" into the output log window.

- Unloading native module on-the-fly can crash the editor



Credits:
--------------------------------
- Neil Moore alias CaptainMigraine
  Initial idea / requests for scaling his map DM-Lea to match some changes to the movement scale