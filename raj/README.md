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
