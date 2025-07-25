# Character Controllers:
Built-In: Is a premade solution that as all the needed character movement specific.
- Only move how it tells
- Simple Move apply gravity
- It can handle stairs and sloops but doesn't slide down the the slope can't walk up.
- Has the touching ground settings.
Rigid body: Interact with the physics engine off rip.
- The main different from a dynamic and kinematic is dynamic take all force. But the kinematic only give force.
- the kinematic only move as the script tell it too.

For both built-in and kinematic there's no drag or momentum
and gravity isn't automatic.

# Built-in Character Controller:
- First this character controller controls collisions and movement.
- For side movement the rigid body is better because the built-in controller doesn't allow for Y axis rotation.
- The min move distance is the smallest change in distance for the character to move.
-  Skin width is to prevent character getting suck in other collision boxs.
- Skin width is recommend to be 10% of the value of raduis.
- Step offset is what control how high the character can climb. 
-  Delect collisions is use to disable or enable collision detection.
- Overlap Recovery Enables or disables overlap recovery. Enables or disables overlap recovery. Used to depenetrate character controllers from static objects when an overlap is detected.
- Collision flags: What part of the capsule collided with the environment during the last CharacterController. Move call.