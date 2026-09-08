---
layout: page
title: "Machine Learning Project - ENPH 353 Competition"
---

# Machine Learning Project - ENPH 353 Competition

### Skills
ROS · OpenCV · Machine Learning · Tensorflow/Keras · Linux · Python

### Description and Outcome

Github Repositories: 
* [ENPH353_Controller_Pkg](https://github.com/AbigailAdam/ENPH353_Controller_Pkg)
* [ENPH353_CNN_Trainer](https://github.com/AbigailAdam/ENPH353_CNN_Trainer)

This project was completed for ENPH 353. In this course, students form teams to build autonomous robots that participate in a competition simulated in Gazebo. The [2025 Competition](https://projectlab.engphys.ubc.ca/enph-353/) involved the robots navigating a complex course while finding and processing clues to solve a fictitious crime. The publication of these clues to a specific ROS topic is how robots recieve points in the competition.  

This all occurs in a Linux environment (specifically Xubuntu 20.04), and the course required a lot of bash scripting and customisations to the system to make running and debugging the simulation simpler. 

These robots operated based on input from two cameras and several LiDARs. The camera input is the most important to the detection and processing of the clues, as they are located on boards placed throughout the course. The robot's decision making is based on a finite state machine which uses the clueboard detections to transition between neural networks trained to drive each section of the course using imitation learning. 

| <img src="/images//enph_353_course.png" style="height:400px; width:auto;"> | <img src="/images/debug_and_comp_353.png" style="height:400px; width:auto;"> |
|:---:|:---:|
| Image of the simulated competition environment with important sections labelled | A screenshot showing the robot in the competition environment (simulated in Gazebo) with the debug UI I wrote to evaluate the detection process |

My responsibilities focused on the clue recognition module of the robot. This involved designing ROS nodes that took in images from the camera, identified if they could contain a clueboard, and if they did read the text it contained. 

The identification of clueboards was done using a mix of image processing checks and input from the LiDAR, which searched for regions of linearly increasing distance that are indicative of flat surfaces. The main steps in the image processing section are illustrated below:

<figure>
<img src="{{ '/images/image_processing_drawio.jpg' | relative_url }}" alt="Debug and Competition Setup">
<figcaption>
A screenshot showing the robot in the competition environment (simulated in Gazebo) with the debug UI I wrote to evaluate the detection process
</figcaption>
</figure>

The reading was done using a convolutional neural network (CNN) constructed using TensorFlow and Keras, and trained using Google Colab. For further details, see the technical report detailing the design and execution of the robot:

<iframe 
    src="{{ '/papers/Team_18_ENPH_353_Final_Report.pdf' | relative_url }}"
    type="application/pdf" 
    width="100%" 
    height="600px" 
    style="border:none;">
</iframe>


