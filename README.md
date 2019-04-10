# README 

![control_arm](https://github.com/phchoi/drlnd-continuous-control/blob/master/reacher.gif)

This project is aimed to solve a problem of how to continuously control a double-jointed arm to move to target locations.

In the beginning, the arm will only randomly perform different action towards random location, however we will need to train it up to stick with the location such that it will continuously stick with the ball on the picture shown above.

## How to train
There are two versions available for this environment, one contains 1 control arm (1 agent) and another contain 20 control arms (20 agents). We will explore and see if it makes any differences to train 1 agent vs 20 agents at once.

## Observation Spaces and Rewards
In order to get better picture on where the control arms are going to and where it is, the arm have 33 variables corresponding to its states, namely position, rotation, velocity and angular velocities of the arm. Each action of the arm will be represented with four numbers, correpsonding to torque applicable to two joints. If the arm successfully maintain its goal (keep touching the ball), a reward of +0.1 will be given and our model will aim for a reward of 30+ which we will call the problem solved.

## Getting started

1. Clone the code base
https://github.com/phchoi/drlnd-continuous-control

2. Environment setup
Please follow the document [here]( https://github.com/udacity/deep-reinforcement-learning#dependencies)

3. Download the Unity Environment

    Version 1: One (1) Agent

    Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip) / 
    Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip) / 
    Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip) /
    Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

    Version 2: Twenty (20) Agents

    Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip) /
    Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip) /
    Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip) /
    Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)
    
    Then, place the file in the code directory and unzip (or decompress) the file.

4. Run the [Continuous_Control.ipynb](https://github.com/phchoi/drlnd-continuous-control/blob/master/Continuous_Control.ipynb) in jupter notebook and follow the instructions to learn how to use the code to train the agent


