## Version 5.1.0
Fixes a bug that would cause completion transitions to fire for composite states that were not complete.

Changed the file management for releases: the latest version will always be state.js and state.min.js and state.d.ts; files with version numbers will also be available.

Renamed IContext to IActiveStateConfiguration, Context to StateMachineInstance.

Added an optional name parameter to the StateMachineInstance constructor and a toString method to return that name.

Cache the fully qualified element name during the bootstrap process (as its used in the StateMachineInstance class).

Simplify transition bootstrap logic by inlining bootstrapEnter.

Removed explicit var typing where implicit is sufficient.

Removed Behaviour type and just used Array of Action in place.

Remove Selector type and functions; replace with virtual methods on Vertex subtypes.

Implement a visitor pattern for state machine models.

Migtated transition bootstrap to a visitor.

## Version 5.0.1
Fix bug relating to external transitions and orthogonal regions that could result in an invalid current active state.

Remove protected keywords due to a lack of tool support for it. 

## Version 5.0.0
Version 5 is a complete re-write from version 4.x.x:
- Much better performance by pre-computing all steps required during a state change. A clean/diry state is maintained  and re-computing possible if the machine strucutre changes.
- The API has changed to a fluent style enabling transitions to be defined in a more natural way.
- The code is authored in TypeScript; this hopefully will lead to better quality code. State machines using state.js can be authored in JavaScript of TypeScript.