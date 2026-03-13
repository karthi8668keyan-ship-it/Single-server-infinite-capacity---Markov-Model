# Single server with infinite capacity (M/M/1):(oo/FIFO)
## Aim :
To find (a) average number of materials in the system (b) average number of materials in the conveyor (c) waiting time of each material in the system (d) waiting time of each material in the conveyor, if the arrival  of materials follow poisson process with the mean interval time 12 seconds, serivice time of lathe machine follows exponential distribution with mean serice time 1 second and average service time of robot is 7seconds.

## Software required :
Visual components and Python

## Theory:
Queuing are the most frequently encountered problems in everyday life. For example, queue at a cafeteria, library, bank, etc. Common to all of these cases are the arrivals of objects requiring service and the attendant delays when the service mechanism is busy. Waiting lines cannot be eliminated completely, but suitable techniques can be used to reduce the waiting time of an object in the system. A long waiting line may result in loss of customers to an organization. Waiting time can be reduced by providing additional service facilities, but it may result in an increase in the idle time of the service mechanism.

![image](1.png)

This is a queuing model in which the arrival is Marcovian and departure distribution is also Marcovian,number of server is one and size of the queue is also Marcovian,no.of server is one and size of the queue is infinite and service discipline is 1st come 1st serve(FCFS) and the calling source is also finite.

## Procedure :

![imAGE](2.png)



## Experiment:


 
## Program
````
# Getting Inputs
ArrivalTime = int(input("Enter mean inter arrival time (secs): "))
MachineTime = int(input("Enter service time of Lathe Machine (secs): "))
RobotTime = int(input("Enter service time of Robot (secs): "))

# Total service time
TotalService = MachineTime + RobotTime

# Lambda and Mu
Lambda = 1 / ArrivalTime
Mu = 1 / TotalService

print("Lambda =", round(Lambda,3))
print("Mu =", round(Mu,3))

if Lambda < Mu:

    Ls = Lambda / (Mu - Lambda)
    Lq = (Lambda**2) / (Mu * (Mu - Lambda))
    Ws = 1 / (Mu - Lambda)
    Wq = Lambda / (Mu * (Mu - Lambda))

    print("Average number of materials in system =", round(Ls,2))
    print("Average number of materials in conveyor =", round(Lq,2))
    print("Waiting time in system =", round(Ws,2),"secs")
    print("Waiting time in conveyor =", round(Wq,2),"secs")

    print("Probability system busy =", round(Lambda/Mu,2))
    print("Probability system empty =", round(1-(Lambda/Mu),2))

else:
    print("Overflow will occur")
````
## Output :
~~~
Enter mean inter arrival time (secs):  12
Enter service time of Lathe Machine (secs):  1
Enter service time of Robot (secs):  7
Lambda = 0.083
Mu = 0.125
Average number of materials in system = 2.0
Average number of materials in conveyor = 1.33
Waiting time in system = 24.0 secs
Waiting time in conveyor = 16.0 secs
Probability system busy = 0.67
Probability system empty = 0.33
~~~
## Result :
Thus the python program is implemented and executed successfully
