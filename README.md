# Project Midori
## Devlog 1: tilesets, animations, movement
date: 08/07/2026
~
we now have a working movement input system. hooray!
the biggest problem i faced was when the player animator's idle clip animation: transform Y position values were affecting the rigidbody2D movements.
by removing those position values, i was able to fix the movement, but am still unable to figure out how to override the animator.
i left a comment on the youtube channel: game code library, asking for a solution, so hopefully someone will reply!
my next goal is to figure out how to expand the map hehe.
youtube link: https://youtu.be/HAVp6Z8b4xA?si=q_MjvsIu6kanvkWQ&t=2397
timestamp: 39:57
~
## Devlog 2:
date: 08/10/2026
~
today, i'm working on camera movement system using cinemachine, a unity package!
using this package, i created "CmCam" using the 2D camera provided.
i dragged the player from the hierarchy into the "follow" box, and it was just as simple as that, whew.
to create map bounds, i added an extension on CmCam called the "Cinemachine Confiner" (do not use the 2D version!).
I created empty objects called "MapBounds" to start making sub-objects that had the "Polygon Collider 2D" component.
because my map is basically a rectangle, i made sure that under Points < Paths < Element < Size = 4.
also, make sure to check the "IsTrigger on the polygon collider so that the player can exist within the bounds.
And lastly, drag the sub-object into the confiner to make the camera follow the polygon bounds!
//
now i'm moving onto the next step, creating map transitions..!
so far, i made another duplicate map boundary for a forest area.
i added a sub-object to T1, called "F1_WayPoint" and added a box collider 2D component (make sure to check IsTrigger!).
to this waypoint, i'm creating a script called "MapTransition" so that it can affect the CmCam.
now, i've added switch cases to the script, to add a bit of distance to my player position when transitioning between bounds.
this is so that the player does not glitch between the empty space within the two waypoints.
timestamp: 58:45
~
## Devlog 3:
date: