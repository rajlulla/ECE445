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


## Week of 3/7


### 3/8

I started working on collecting the data using Arduino. I did not have any experience in Arduino as well so I spent a couple of hours learning about that.

After having some knowledge of Arduino circuits, we discussed how we wanted the data to be recorded(data format) in order to make it easier for Raj and me to implement the algorithm.

We conclude on the format of data shown below:


<table>
  <tr>
   <td>Is a spike occurring?
   </td>
   <td>0 or 1
   </td>
  </tr>
  <tr>
   <td>Current draw
   </td>
   <td>In amps, could be 0-20
   </td>
  </tr>
  <tr>
   <td>X acceleration
   </td>
   <td>In m/s/s
   </td>
  </tr>
  <tr>
   <td>Y acceleration
   </td>
   <td>In m/s/s
   </td>
  </tr>
  <tr>
   <td>Z acceleration
   </td>
   <td>In m/s/s
   </td>
  </tr>
  <tr>
   <td>X rotation
   </td>
   <td>Scale of 0-1
   </td>
  </tr>
  <tr>
   <td>Y rotation
   </td>
   <td>Scale of 0-1
   </td>
  </tr>
  <tr>
   <td>Z rotation
   </td>
   <td>Scale of 0-1
   </td>
  </tr>
  <tr>
   <td>Temperature
   </td>
   <td>In Celsius
   </td>
  </tr>
</table>



### 3/10

I started to build the Arduino circuit to collect the data. I also worked on understanding the MPU6050 unit and wrote some starting code for it.

I went ahead and ordered an SD card as well. We wanted to use a network like Bluetooth to transmit the data that we are recording to our database but we figured that that would not be a viable option because our batteries are supposed to be used by any drone out there, the network would be a constraint to the transmission of the data. While trying to work with Bluetooth for example, the maximum range of it was 33 feet.


## 3/11

Worked on circuit to store data to an SD card. See "circuit" image

## Week of 3/21


## 3/24

We received the SD Card module before spring break so I started using that in the circuit to collect data on it just after SpringBreak. Here is a snippet of the code that I implemented to record the data in the SD card:

See "code" image


## Week of 3/28


## 3/28

Helped Namin put in the PCB request.

Worked on writing the individual progress report


## 3/29

Run our first flights and recorded the data while flying them on the SD card using my code.

It was hard to fly the plane because we were not professionals. We decided after that to run fake flights - I would just hold the plane and Namin and Raj would throttle it up and down.


## 3/30

Finished writing my individual report and submitted it.

Collected the data from our first flights and fake flights. Then extracted it from the SD card to work on it with Raj and started to think about the algorithm.

Here is a summary of the data we recorded on that day:


<table>
  <tr>
   <td>LFP Start V
   </td>
   <td>NCA Start V
   </td>
   <td>LFP duration
   </td>
   <td>NCA duration
   </td>
   <td>LFP end V
   </td>
   <td>NCA end V
   </td>
  </tr>
  <tr>
   <td>12.6 V
   </td>
   <td>12.6 V
   </td>
   <td>45 s
   </td>
   <td>13 s
   </td>
   <td>12.4 V
   </td>
   <td>12.4 V
   </td>
  </tr>
  <tr>
   <td>12.4 V
   </td>
   <td>12.4 V
   </td>
   <td>12 s
   </td>
   <td>30 s
   </td>
   <td>12.4 V
   </td>
   <td>12.1 V
   </td>
  </tr>
  <tr>
   <td>12.4 V
   </td>
   <td>12.1 V
   </td>
   <td>30s
   </td>
   <td>27s
   </td>
   <td>12.2 V
   </td>
   <td>11.9 V
   </td>
  </tr>
</table>



### 3/31

We ran more fake flights again to get more data.

Here is a resume of the flights we ran:


<table>
  <tr>
   <td>LFP Start V
   </td>
   <td>NCA Start V
   </td>
   <td>LFP duration
   </td>
   <td>NCA duration
   </td>
   <td>LFP end V
   </td>
   <td>NCA end V
   </td>
  </tr>
  <tr>
   <td>11.9 V
   </td>
   <td>12.3 V
   </td>
   <td>78 s
   </td>
   <td>10 s
   </td>
   <td>11.5 V
   </td>
   <td>12.2 V
   </td>
  </tr>
  <tr>
   <td>11.5 V
   </td>
   <td>12.2 V
   </td>
   <td>5 s
   </td>
   <td>41 s
   </td>
   <td>11.5 V
   </td>
   <td>11.8 V
   </td>
  </tr>
  <tr>
   <td>11.5 V
   </td>
   <td>11.8 V
   </td>
   <td>60s
   </td>
   <td>5s
   </td>
   <td>11.1 V
   </td>
   <td>11.8 V
   </td>
  </tr>
</table>

## Week of 4/4

At this point my work on the hardware part was done. The data were correctly recorded. So I started to give Raj some help on the algorithm part.

At first, we started using a basic linear regression algorithm
