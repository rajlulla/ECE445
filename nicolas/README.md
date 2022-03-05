## Week of 1/24 to 2/7

Worked on the project proposal

Finalized the project proposal and submitted it for the team


### 2/14

Worked on the design document

We went through the specifics of the project and what was possible to accomplish in the time given to us


### 2/16

Met as a group to continue working on design document

We worked on the subsystems requirement


### 2/18

We created block diagrams

We finished the design document

We focused on cost and schedule parts of document

## Week of 2/21


### 2/22

We attended design document check

We implemented the changes advised to us form the design check

Having mostly a software engineering background, I started reading about how to use an STM32 to collect data from our different sensors and write it into an SD card. I chose to go with the STM32 because it has a very low power consumption


### 2/24

Finalized the design document and submitted it as a team

I worked on the soldering assignment and demonstrated it to TA. The soldering assignment took me a good 6 hours.

## Week of 2/28


### 3/2

Attended design review meeting

Decided that we would need positional data about the flight of our planes outside of the current and voltage. We opted for an MPU6050 chip. Started reading how to interface that with the STM32 and understood the code for initialization of the MPU using the WHO_AM_I register.


### 3/3

Determined all the types of data that would be necessary for us to have an effective algorithm

We chose the _current, voltage, acceleration(x,y,z), velocity, x, y, z position_

_Decided to write my own drivers for the devices _that were going to be connected to the STM32.

Implementing the drivers for sensors in our project revealed itself to be more complex than I thought because of the complex connection between peripherals. So I decided to just use an Arduino to prioritize the completion of our project. Since our algorithm was mainly based on collecting the flight data.
