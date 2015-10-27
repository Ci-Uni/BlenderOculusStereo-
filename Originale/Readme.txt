
This is a crude Oculus DK2 head tracking support for BGE by Mārtiņš Upītis (martinsh) v1.0
it relies on "python-ovrsdk" by Brad Davis (jherico) found here https://github.com/jherico/python-ovrsdk
I have modified "python-ovrsdk" slightly to support newer Python versions
it should work on Windows, MacOS and Linux and is tested on recent Blender versions

this blend includes:
- dk2_distortion.glsl - takes care of the distortions caused by lenses in DK2
- fps.py - gets framerate and prints it on the table
- vr.py - reads head tracking data from Oculus sensors and moves the Camera
- and the Readme file you are reading now

how to run this file:
- connect Oculus Rift DK2 to our computer, make sure Oculus drivers are installed
- open this file
- put DK2 on and press P with mouse curson in your DK2 screen
- "esc" button will end the game
- "spacebar" re-centers the tracking

how to set up in your project:
- put "oculusvr" folder in the same directory as your blend file
- copy "Camera", "translate", "VR" and "track_cam_frustum" objects from this file to your scene
- parent "translate" object to your player

notes:
- if you have DK2 connected, when opening this file, a separate Blender view should open full-screen in your DK2
- sometimes head tracking is smooth, sometimes juddery. I think it is a sync issue between tracking and rendering
- when changing camera position in the scene, make sure you move "translate" object. You will then have to Clear 
parent (Alt+P) (Clear and Keep Transform) of the Camera and parent (Ctrl+P) it back to "translate"
Annoying, but I have not found a better way to do that yet
- DK2 has a horizontal field of view of 90°, so for best experience set your camera angle to 90° (16.00 mm)
- Interpupillary distance or IPD (Eye Separation in Blender) does impact quite alot how you precieve scale of the scene.
For each individual it changes, but I found that value of 0.065 is a good average that fits most
- If you experience a discomfort after prolonged use of Oculus DK2, I`d suggest stop using it and take some rest.
when I was working on a demo file for two days, I noticed discomfort, but ignored it. As a result I had a bad migraine :) 
(the head tracking was not yet done though)
-the "track_cam_frustum" object is optional, you can exclude it from your project, but then in "vr.py" delete 
all after line 102 (where debug thing is starting)


thanks Dalai Felinto (dfelinto) for getting me into this
that`s it for now.

You are free to use this setup as you like.

Have fun,
martinsh

