# 1. Cells

In the old days of VHS tape, a typical movie is recorded on a spool of tape to view from 
the beginning to the end in a sequential fashion. The movie actually is made up of many 
individual sequential segments of video scenes or film clips. The only interaction one can 
have with a VHS tape is rewinding and forwarding to the scenes of interest and play 
back. From the film editor's perspective, each individual scene is a basic building block, 
interconnecting with other scenes to produce the entire movie. In the DVD terminology, 
this individual scene is called a cell. Most if not all authoring packages require cells to 
contain a segment of video. The video may or may not have accompanied audio. From 
the DVD author's perspective, a cell is the smallest element of a DVD project. On each 
DVD, a cell is a unit of playback of real-time data and is uniquely identified by a set of 
numbers: cell identification or simply cell id (from 1 to 255) and Video Object Unit 
identification or simply VOB id (from 1 to 65535). The meaning of cells and video object 
units and the usage of cell id and VOB id are explained in subsequent sections. 
 
The DVD specifications require the video and its optional audio component to be 
recorded in specific data formats. A cell can be accessed randomly from any position of 
the DVD. The playback duration of a cell can be less than a second or several minutes 
long. Theoretically, a cell can contain an entire movie. At the end of the cell playback, a 
cell can request the DVD player to perform a specific task via its cell command. A cell 
command is a sequence of 8 bytes of binary data which can be one of the many 
commands provided by the DVD virtual command set. There are certain restrictions on 
cell commands depending upon where the cell is on the disc. The DVD specifications 
define a set of 

virtual machine (VM) commands

 which can instruct the DVD player to 

set, verify certain playback conditions or user options, and navigate or modify the 
playback sequence accordingly. The presence of cell command is optional. This is how 
user interactivity is achieved. For example, a cell can play itself indefinitely until the user 
presses "stop" on the remote control. This is done by issuing a cell command to retart the 
playback of itself at the end of the cell. A cell command can request the DVD player to 
skip over a group of cells so that these video segments can never be played back even 
though they exist on the DVD. The possibilities are endless. 
 
A cell can optionally have a 

mask and highlight

 layer to simulate the behavior of a push 

button in menu selection and the highlighting of certain display items for interactive 
navigation. A cell is a very important DVD data structure with many roles and functions 
and will be explained in more details in subsequent sections.

There are two types of cells: single-angle and multi-angle cells. In the following example, 
the playback of cell 1 starts at 2 minutes, 59 seconds, and 10 frames after the disc is 
inserted into the DVD player. Similarly, cell 2 starts after 3 minutes and 19 seconds. Cell 
1 and 2 are single-angle cells because they offer only one version or view (angle) of the 
video to play back. Cell 3 is a multi-angle cell since at the time line after 3 minutes and 
39 seconds, one of the video versions 3-1, 3-2, or 3-3 can be played back depending upon 
the setting of the DVD player. The default selection of the video angle is usually 
initialized when the disc is inserted and can be changed in many ways, one of which is 
the use of cell command. A cell command is executed after the cell has been played back. 
Cell 1 and 3-2 (second angle) have cell commands. A cell can have one or more audio 
tracks independent of the video angle. 

![graphic](1.png)

The playback between cells can be seamless or non-seamless. Seamless play refers to the 
smooth, uninterrupted, and continuous flow of sound and video images during the 
playback of a disc in a DVD player, with no noticeable pauses, breaks or jumps. 
Seamless play is preferable in most situations, but it is not possible in all situations due to 
the many constraints of the DVD technology, both in hardware limitations and the 
recorded data format. Non-seamless play means there is a momentarily pause or 
interruption in the flow of play. This usually occurs at the beginning of playing back a 
non-seamless cell. Cells that contain highlighting information for menu buttons are non-
seamless by default. Non-seamless play is unavoidable in many situations which will be 
obvious in later sections of this guide.
