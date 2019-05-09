#### Problem 1

##### (a) Describe the optimal substructure of this problem

Optimal substructure: 

n = the number of steps in the experiment

We can split the n steps to a set of sub steps S = {k<sub>1</sub>, k<sub>2</sub>, k<sub>3</sub>….k<sub>j</sub>} 

n = k<sub>1</sub> + k<sub>2</sub> + k<sub>3</sub> + …. + k<sub>j</sub>

Each element in the set S has the <span style="color:red">**longest continuous**</span> signed up value, that means no switch in any k.

So we can make sure we have the least switches.

For any k<sub>1</sub>, k<sub>2</sub>, k<sub>3</sub>….k<sub>j</sub> , it only associate with one student.

##### (b) Describe the greedy algorithm that could find an optimal way to schedule the students

At the beginning of scheduling,  we have 3 inputs:  numStudents, numSteps, signUpTable (lookup table).

Our goal is to find the longest continuous 1's.

For example 1, signUpTable is : 

{ 

{0, 0, 0, 0, 0, 0, 0},

{0, <span style="color:red">**1, 1, 1,**</span> 0, 1, 0},

{0, 0, 1, 1, 1, 0, 0},

{0, 1, 0, 0, <span style="color:red">**1, 1, 1**</span>}

}

Step 1:  create another 2-d array to store our schedule results called scheduleTable.

Step 2:  from step 1, student 1, use iteration to find the longest continuous 1's in look up table. Get the steps number maxSubStep.

​              for i from 1to numStudents

​                for j from currentStep to numSteps

​                   if signUpTable [i] [j] equals 1

​                     tempStep++

​                   else break

​                   if maxSubStep < tempStep

​                   maxSubStep = tempStep;

Step 3: find the current step, currentStep = currentStep + maxSubStep, currentStep from 1.

​             From  current step to next maxSubStep, 

​             repeat Step2.

Step 4: After n Steps, we get our results.

##### (d) What is the runtime complexity of your greedy algorithm? Again, you don't need to factor in the setup of the lookup table, just your scheduling algorithm.

​      The runtime complexity is n<sup>3</sup> , in my function I have 1 while loop nest with 2 nested for loop.

##### (e) In your PDF, based on your answer to part b, give a full proof that your greedy algorithm returns an optimal solution.





#### Problem 2

##### (a) Describe an algorithm solution to this problem. Feel free to talk about how you would adapt an algorithm we covered in class.

I checked *shortestTime* function, this function Dijkstra algorithm,  and found I still can use Dijkstra algorithm for myShortestTravelTime with  just adding waiting time. Because for each step, waiting time  relates freq , arriveTime , firstTrainTime, this is all given from station u to v.