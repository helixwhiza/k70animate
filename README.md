# CUE-Animate
A series of python scripts to produce and display animations on Corsair RGB keyboards via CUE on Windows.

#Requires

-Python 3

-numpy, cue_sdk and Pillow libraries (install via pip)

-Corsair Utility Engine (CUE) must be running

-CUE SDK (seperate download from http://www.corsair.com/en-au/support/downloads)

-The system environment variable CUESDK must be set to the location of the sdk folder.

#Usage
Animations are stored as ~111px wide PNG images (for US layout, others may differ). Each row represents one frame of the animation.

Simple animations can be generated using pan.py and spin.py from any existing image, either scrolling across your keyboard or spinning in place respectively. The usage of these scripts is:

`python pan.py INPUT_IMAGE_PATH OUTPUT_IMAGE_PATH [FRAMES_IN_ANIMATION]`

To convert a simple single image to a displayable layout simply use layout.py

`python layout.py INPUT_IMAGE_PATH OUTPUT_IMAGE_PATH`

Any suitable image can be displayed on your keyboard using 'display.py', by default it runs at 10 fps but this can be modified with a command line argument.

`python display.py ANIMATION_IMAGE_PATH [FPS]`

#Extension
`layout.py` can be used to easily write animation producing scripts. The function `layout.create` takes in a single PIL Image object of any size, resizes it as necessary and returns a single numpy array representing the frame of the animation. For an example see `spin.py` and `pan.py`.
