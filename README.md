# Final Project

## Instructions

This repository is a stub for your final project. Fork it as a template for your project, and develop your code in the forked repository. For details on how to fork and turn in the project, see section 3 of the github education  [documentation](https://education.github.com/guide/forks). After you fork the repository, please enable the issue tracker in the repository settings so that others in the class (including the professor) can provide feedback.

Expand on the readme questions below to provide an overview of the goals, background, and challenges for the final project. You can delete the questions as you write text that answers them, or leave the prompts in place. You can also delete this instruction section of you like.

## Introduction

This is a final project for the [Interacting with Data](https://github.com/Brown-BIOL2430-S04-Fall2015/syllabus) seminar in fall 2015. This project stems from my goal to create an animation using 3D coordinates of bony landmarks that are captured using motion capture as well as visualizing the ground reaction forces that recorded using an instrumented treadmill. 

To view this project, ... (embed visualization here or provide instructions on how to view the project). Visualization, or my attempts at it, is still underway.

## The data

Description of data...

- Data source (unpublished)

Arellano, C. J., & Kram, R. (2014). The metabolic cost of human running: is swinging the arms worth it? The Journal of Experimental Biology, 217(Pt 14), 2456–2461. http://doi.org/10.1242/jeb.100420 
//CHANGE THIS CHRIS

- Data structure

Methods: The data comprises the 3D coordinates of 27 reflective markers that were placed on specific landmarkers on the body while human subjects ran on a treadmill for a total of 7 minutes. Data were collected at 100 frames per second for 30 seconds using an 8-camera motion capture equipment and software commercially available by Motion Analysis Corporation Inc. 

File Format: Data output is saved as a ".trc" file, which stands for "Track Row Column". The file consist of 6 rows of header information followed by rows of data that consist of the following:
		
		[sample # time X1 Y1 Z1 X2 Y2 Z2 ... X27 Y27 Z27] 

## Background

Examples of previous visualizations of similar data or processes, if any exist... Include links or add images to markdown document... how were data mapped to aesthetics in these previous approaches? Was there filtering?

My visualization is inspired by one of Mike Bostock's creations free available at the following:  

	http://d3js.org/ --user-action--> click on Examples link
	https://github.com/mbostock/d3/wiki/Gallery --user-action--> click on Motion Chart graph
	http://bost.ocks.org/mike/nations/ --user-action--> see amazing time-varying changes in "Weath & Health of Nations" between 1800 to 2009.

My goal is to this code to replicate a previous animation I created using Matlab. My animation shows the position of the body markers as a function of time as a human subject walks with and without mechanical arms. The limitation of this view is the absence of data interaction between the user and the animation. My previous image, take from a still frame, can be found on my personal website:

<img src="http://christopherarellano.com/animations/walking_100-poster.jpg" alt="Arm Swing During Walking Showing Right and Left Side of the Body">
	

Shortcomings of previous approaches, or potentially interesting gaps between previous approaches...

1) Visualization plays in its entirety without the user being able to stop, pause, play
2) Freezes at the end so user has to refresh the link in order for visualization to play again
3) When scrolling over individual circles, identification of names, size, does not appear to user so mapping of data to particular characterisitics is not available.

## This project

### Mapping of data to aesthetics

How will aesthetic attributes ( X / Y / color / shape / size /texture / etc ) will be mapped to the data?

Aesthetic attributes will be mapped to the data by the following strategy:
	1) X-Y: 3D position data will be simplifed by viewing only the x-y coordinates which will give the user a side-view visualization of a human subject walking on a treadmill
	2) Color: x-y coordinates as a function of time will be given blue color for upper and lower lower limb markers. 
	3) Line: Right side of body will be given solid line and left side of body given dashed lines

### Filtering

Are data filtered? ie in some views are some data not mapped to particular attributes of the image? What is the goal of the filtering?

Data are filtered using standard-techniques in the biomechanics field. For this particular data-set, the x, y, and z position for each reflective marker is filtered using a 9th order, zero-lag low-pass Butterworth filter with a cutoff frequency of 6 Hz.

### Extra ink

Are there aesthetic attributes that are not mapped to the data? If so, what purpose do they serve ( redundancy for robustness / improve visual metaphor / but data in context / beauty / etc )?

The z-coordinate is not mapped due to my inherent 2-D visualization abilities using D3. In future iteration, I plan to explore methods to create 3-D visualization using D3.

To be created: 

A reference frame in the left corner (still thinking about incorporating into the visualization) will be implemented to provide the user the global coordinate system.

A button (play, stop, and pause actions) would be useful to give the user control of playing the animation.

Header information will be incorporated to give user name of walking trial, given step frequency at fixed speed, and whether humans walking with biological or mechanical arms.

Are any data mapped to more than one aesthetic attribute? Why?

Currently, only data is mapped to x-y coordinates but a possibility is to include the z-coordinate by mapping the radias of the circle. The idea here is that the radius will change size as the markers moves in and out of this particular coordinate giving the user information about how the arm abducts/adducts during the swing cycle.

### Motion

If motion is used, what purpose does it serve ( metaphor (eg representing motion in real world) / transition continuity between views / etc )

### Perspective

To what extent is perspective (eg mappings) controlled by users vs hard coded in advance? How does this project aid in exploration vs exposition?

At this visualization's early stage, time will be the only mapping controlled by the user. I hope to include a button that will allow the user to play, stop, pause and perhaps even insert the ability to start at specific time.

All other attributes will be hard coded in advance but in future iterations, my goal will be to add user controlled mapping of joint angle data. For example, the user may be able to highlight the ankle, knee, hip, or elbow joint and a time-series plot wil magically appear. Furthermore, the time-series plot can be displayed for the left and right side (a user controlled option) to aid in data exploration.

## Assessment

Was the new visualization successful at providing insight that was not possible or more difficult with previous approaches?

To be addressed. 

What are the main limitations of new approach?

Learning curve and potentially hard coding the algorithms to provide joint angle data. One way to work around this that I already have the data exported my previous Matlab programs.

What are future directions this could go in?

Future directions would include user controlled perspective of 
	
	1) side-view and front-view displays.
	2) multiple displays of joint angle data for upper and lower limbs
	3) perspective controlled by user, i.e. user could rotate the frame of reference while visualization is playing.


