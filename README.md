# UD_HideAndSeek

## Description
This is a udacity project on the topic "Unreal and VR". The player as VR Pawn has to search "his or her lost mobile device". A buzzing sound at the location of the phone as cue is provided. The game may be startet with a big, red button, placed at the wall in front of the player's starting position. A goal-poste is placed near the sink in the kitchen. Found mobile devices have to be placed in the goal to score a point and to respawn a new "lost mobile". A "widget cube", placed on the fridge, keeps track of current time left and current score.
The player is informed with sound cues for:
- the start
- every new lost mobile (random internal timer to buzz)
- the last 20 seconds
- the end of game

## Software and Hardware
The project was conducted with the Unreal Engine 4.15.3, the Oculus Audio Plugin and some additional ".wav files" downloaded from www.freesound.org have been used. The environment was provided by udacity's project team "Learn Unreal VR Foundations" as template. Additional assets (mobile phone, goal poste, and hands) were designed by the project team with ZBrush 4R8 and Maya 2018. The project has been tested with the HTC Vive with a constant framerate of 90 FPS, but should work with the Oculus Rift as well. To optimize render quality and frame rate trade off, motion blur, bloom, auto-exposure and forward rendering as been adapted. Additionally, *VR-best-practices* (https://docs.unrealengine.com/en-us/Platforms/VR/ContentSetup) have been implemented in the *Config\DefaultEngine.INI-File*.

## Blueprints
### General description
The player may posess the bp_MyVR_pawn with two hands, which have a custom animation (ABP_hand_left and ABP_hand_right) to grab. For the game a myVRPlayerController, a myVRCameraManager and a myVRGameMode have been implemented and set up. The player can grab mobile devices with the **motioncontroller trigger**. We used the BPI_My_PickInterface to communicate with the BP_myMobile. These devices are spawnd automatically, when the player starts the game with the BP_starterButton, which keeps track of the game timer. The BP_Goal keeps track of the points, the player may score with placing a mobile phone into the goal. A new mobile device will be spawned at a random point (BP_mobileSpawn - Actor) as references. Whithin the project multiple blueprints connections via casting have been implemented.

### Locomotion System
The VRpawn has an implemented locomotion system based on an line trace. When hitting a horizontal object on ground hight, the player may teleport the actor to this location. The possible teleport location is marked with a green circle on the floor. Press **MotionController Facebutton 1** (on the ThunmbWheel) to predict teleportation and release to teleport. This kind of locomotion is quicker than the one shown in the lectures, the player does not have to wait for an invisible sphere to hit the ground and additionally, with a straigt line, the player has to move around (big) objects, which would be a more realistic kind of locomotion.

## Annotations
This project has been conducted by Dejan Popic and Sebastian Strahm. Both working at the Swiss Distance Learning Universtiy. Last Changes: 06.06.2018
