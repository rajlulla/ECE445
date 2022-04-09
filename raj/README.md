## Week of 2/14


### 2/14

Met as a group to begin working on design document

Established high level requirements and overall goals for project

Wrote out problem statement and generic solution


### 2/16

Met as a group to continue working on design document

Defined subsystems and subsystem requirements


### 2/18

Created block diagrams

Finished design document

Focused on cost and schedule parts of document

## Week of 2/21


### 2/22

Attended design document check

Implemented changes from DDC


### 2/24

Finalized design document and submitted

Worked on soldering assignment and demonstrated to TA


## Week of 2/28


### 3/2

Attended design review meeting


### 3/3

Beginning work on first PCB order with Namin

Established what data we can collect with the circuit
## Week of 3/7


### 3/8

Considering we don't have actual flight data yet, I wanted to still get some progress made relating to the algorithm

After discussing with Namin and Nkiere about the format of the data, we have found that the data will be given in the following format:


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


This data will be used to formulate the basis of machine learning models


### 3/9

As real flight data is still over a month away, I decided to put together some “fake” data to build the models off of. A few lines of this are shown below:


<table>
  <tr>
   <td>time
   </td>
   <td>current
   </td>
   <td>voltage
   </td>
   <td>speed
   </td>
   <td>acceleration
   </td>
   <td>highcapacity
   </td>
  </tr>
  <tr>
   <td>15
   </td>
   <td>31.6
   </td>
   <td>1.3
   </td>
   <td>24
   </td>
   <td>5
   </td>
   <td>0
   </td>
  </tr>
  <tr>
   <td>16
   </td>
   <td>35.2
   </td>
   <td>1.3
   </td>
   <td>31
   </td>
   <td>7
   </td>
   <td>0
   </td>
  </tr>
  <tr>
   <td>17
   </td>
   <td>38.8
   </td>
   <td>1.3
   </td>
   <td>38
   </td>
   <td>7
   </td>
   <td>1
   </td>
  </tr>
  <tr>
   <td>18
   </td>
   <td>42.4
   </td>
   <td>1.3
   </td>
   <td>45
   </td>
   <td>7
   </td>
   <td>1
   </td>
  </tr>
</table>


Obviously, the values I have here are different from the values I will actually have, but the principles still apply. Next step is to research different ways to analyze this data and start building the basic “machine learning”


### 3/10

I spent the day researching different ways to perform analysis of the data we have collected. Given principles I have learned between CS 411, CS 498, and STAT 200, I determined two main methods to actually perform this analysis:



* Linear regression using scikit-learn or statsmodels
* Using tensorflow to perform regression analysis

Following spring break, I will test these two methods. The linear regression is the backup if I can't manage to get machine learning using tensorflow to work.

## Week of 3/21


### 3/23

Today, I worked to test the linear regression methods of analysis. I tested out scikit-learn and statsmodels. An example output using our fake data from a statsmodels test is shown in the image “statsmodels_output”

While this linear regression does provide a reliable output, using real machine learning in the form of tensorflow would still be preferred.


### 3/25

Tested out using tensorflow to create some sort of machine learning model. Despite spending the whole day trying to figure out how to use tensorflow to process this data, I decided to hold off until we had more data to try again. I found it difficult to get any sort of progress, but maybe getting real data will change the code side. We are planning to fly the plane next week and collect real flight data.


### 3/26

Worked on individual progress report

## Week of 3/28


### 3/28

Finished individual progress report


### 3/29

First flights

Today we decided to run our first test flights of the plane and quickly realized how difficult it is to actually fly the plane. After a few attempts at flying the plane, we decided the best method is to run “fake” flights, meaning we’ll tether the plane down and throttle it up and down.


### 3/30

We started collecting data running test flights. The data pertaining to beginning and ending voltage is shown below:


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

We ran a few more test flights to better understand the power draws of each battery


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


### 4/4

Given our findings last week, we have decided to change the approach for the “algorithm” part of the project. I am going to design a python backend with a react frontend to take flight data, process it, and return some metrics to the user.

Today, I wrote a script to take in JSON data and return a linear regression summary to the user. This script is in linear_regression.py


### 4/6

Today, I began work on the react frontend where we will process the data collected from the plane. I created the base structure of the react app and wrote the code to allow the user to upload a CSV and process it into a javascript array. The next step is to process this data into graphs for the user to see.


### 4/7

Today, I wrote the code to take the javascript arrays and process the data into graphs where the user can visualize their flight. An example of this is in the image “visualizations”.
