# Automated Repair of Feature Interaction Failures in Automated Driving Systems


# Authors 
## 1.(Raja Ben Abdessalem, 

## 2.Annibale Panichella, 

![Author Image](./image1.jpg)
## 3.Shiva Nejati, 

![Author Image](./image2.jpg)
## 4.Lionel C. Briand, 
## 5.Thomas Stifter)

## [Confrence]
### (ISSTA 2020 Technical Papers)

>Venue:Mon 20 Jul 2020 13:50 - 14:10 at Zoom - REPAIR AND DEBUG 
#### Chair(s): **_Xuan Bach D. Le_**

# Abstract

>In past time several automated statrgies have been proposed to fix bugs without any human intervention.
There describes how to resolve issues regarding system levels.These failures are common complex systems.
Here in this paper authors proposed a repair technique to automatically resolve undesired feature interaction failures in (ADS).

### Some repair startgies are:

1.Localizing faults spanning several lines of code

2.Simultaneously resolving multiple interactionfailurescausedbyindependentfaults

3.scaling repair strategies from the unit-level to the system-level

4.)resolving failures based on their order of severity 


## Introduction

>Automated driving system is often several units of functionality features known as ADS that automate specify driving tasks e.g Emergency brakes,traffic light cruise control and Artificial intelligence should also b envolved to know the enviroment information such as pedestarian speed,position of the car road structure lanes.This information should be useful for ADS feature to know car maneuver.Cruise control feature control car acceleratin speed while at the same time traffic recognization features helps to stop car when traffic light turn red.Some integrations rules are applied to resolve maneuver conflicts.Integrations rules provide us that which feature should be priortized according to condition such cruise control for speed traffic light recognization for traffic.The should should be come in contact with system after measuring enviroment information.Integration rules tend to diffuclt as they should provide large numbers of enviroment traffic light recognization.There needs to assist engineers as they repair integration rules for every situation they priortize maneuver that can ensure ADS saftey.Recentaly many approaches have been proposed to resolve fault in software systems.

## 1..The repair technique should localize faults spanning     multiple lines of code.

>Most Program techniques are spectrum-based techniques this is for single faulty program statement not for multiple.They may not identify fault in multi-statement.

## The repair technique should be able to fix multiple independent faults in the code 2.

>All patches and test suits are failing because of using single fault or patch at a time test suit. In ADS integration code fails due to presenece of multiple faults located in the different parts of code.We have to fix more than one  fault in the code. 

## 3. The repair technique should scale to fixing faults at system-level where the software under test is executed using a feedback-loop simulator.

>Simulation testing means to autonomous vehicle Testing Virtual verification services to ensure autonomous vehicles are road safe.Weather conditions and traffic situations.

## 4.The repair technique should resolve failures in their order of severity.

>In ADS some failures are more crirtical than others as here given example of speed of a car km/h if an accident occurs  someone hits car to pedestarian less than 10km/h it is less crirtical than others.We are priortizing these startgies to avoid accidents.

# 2 MOTIVATION AND BACKGROUND  
The motivation of this paper that we should self drive to test ADS under four objectives cruiese contron,traffic recognization,pedestarian and bracking system.

## 2.1 Motivating case study:

our motivation is to propose a automated softawre system where one car's speed accleration must be averaged according to leading car.Traffic sign recognizations applied acceleration braking and steering commands,Pedistarian it removes accident occurs due to collision of pedestarian and car and braking sytem for sudden brakings.For e.g Autoamted cruise control manages car accelration from leading car at same time if a pedestarian is crossing road braking system avoid hitting car to pedestarian.

Some Ordered integration rules to resolve conflicts between different ADS features.

Each rule activates a simple ADS feature.

These rules work according to enviroment variable
for example a pedestarian detected behind a car the ttc time to collision between objects and speed of both pedesterian and car should be measured if both are in same speed than the dist(p,c) denotes the distance between car and pedistaraian p for pedistarian and c for car.dist(c,sign) denotes the distance between car and traffic sign.Simlarly rule two states that if an object diffrent than pesdestarian is detected in front of car than AEB should be applied.

There is two general ways predicted by wich integration rules may be wrong.

## 1.
>The pre condtions rules may be wrong there is un accuracy in mathematical or relational operators which are used for e.g using < instead of > and + instead of -.For rxample in rule no b  
there is threshold distance is too small means when a pedestarian is detected in front of car there will less chances to avoid accidents.

## 2.
>Applying rules in different order or manner aplying rules in different will put effect on system behaviour.As in rule 3 ACC has been applied which violates car's speed limit and rule 4 TSR has given less priority as compare to rule 3 is never checked and cannot activate TSR.To avoid this situation rule 4 should be priortized over rule 3.

## 2.2 Context Formalization:

ADS tuple has been defined with fragmented trees.leaf nodes choices between alternatives and gives result. As shown in figure 3 showing is a peditarian detected precondtion become true PP become activate if another object in front of car is detected AEB become activate.


>In my perception the motviation of this paper is too good it is useful to avoid many accidents features of ADS are very much good in behaviour like ACC PP AEB TSR the features help us in in saftey driving this should be implemented.

## Approach:
In this section we present approach of ARIEL to repair and faults and faults in the integration rules of ADS.

## 3.1: Fault Localization:
It means localizing faults in code.Here localizing faults means to localize faults in integration rule of ADS that how their behaviour should be and what are the faults here are two ways to localize faults

1.focusing on the path π ∈ Π covered at the time of failure.
2.Considering " the severity of failures"

## 3.1.1.focusing on the path π ∈ Π covered at the time of failure:
failures revealed by test case tc1 means to determine path that belongs cause failure by tc1.
already discussed 2 wrong conditions in image 2 where wrong preconditons and wrong arrangement of rules have been propesed.

## 3.1.2 severity of failure:

In severity of failures there discussed ADS features faults for example if the distance between car and pedestarian is low there more chance of accident so it will focus on distancing and activating AEB.the lower the output the larger the severity values.

## Program Repair: 
It is genetic based technique in popultion evoleves by using genetic programming algoritham.which evolves pool of candidate patches iterratively..Each candidate patch is evaluated against the entire test suite to check whether changes lead to more or fewer failing tests.

N × summation tc ∈TS cost(tc),
Where N is population size and tc is cost test.

Population based algoritham assume that cost of evluating individual patches is not too large.hence test result can be collected within few seconds.

Based on the observations above,we opted fort he(1+1)Evolutionary Algorithm (EA) with an archive.(1+1) EA selects only one parent patch and generates only one offspring patch in each generation.Generating and assessing only one patch  at atime allows to reduce the cost of each iteration, thus addressing O3 in Section1.Our program repair approach,ARIEL,includes(i)(1+1)EA, (ii)our fault localization formula(Equation1),and(iii)thearchiving strategy.Algorithm 1provides the pseudo-code of ARIEL.

ARIEL recieves as input TS and faultyself driving system.
Where ,Π denotes the faulty integration rules.All pases test of output are repair intergration rules denoted by  Π∗.The Algoritham starts by intiazlizing the archieve with faulty rules.In each iteration ARIEL selects only one patch  Πp ∈ archive.and creates one offspring (Πo).   
Then offspring will extract remaining failures by TS and compute them with corresponding object scores.The offspring patch is added to the archive if it decreases the severity of failures compares to the patches currently stored in archive .The  archive and its updating routine are described in details in sub section  3.2.4. These searchs tops when the termination criteria are met(seeSection3.2.5).

## Generating a Patch:
ARIEL generates patches by using routine algorithams by applying Fault Localization formula to determine the suspiciousness.
Using  Roulette Wheel Selection (RWS) we select statment s  s ∈ Π among the most suspicious one.Routlee assigns each statement a probability of being selected for mutation.The probablities are suspiciousness of each statment.These algorithams are very beneficial in ADS it helps us to determine whether faults of self driving systems and features and integration rules of ADS are working on some saftey conditions.

## Search Objectives:
Search objectives identfies each failures occurs while TS which violets saftey requriements.Since ADS have multiple failures/violations.

# Evaluation:
>In this section we evaluate integration rules of ADS using indutria systems.
## Case Study:
In our expriments we used two system with the colaboration of company A.these two systems sontains four rules discussed in section 2.To resolve conflicts among these manuevers two different integration rules has been set.AutoDrive 1 and AutoDrive2.Their features and intergration rules are implemented in MatbLab/Simulink Language.We use Prescan.Prescan is a physics based simulation system that is used in automotive industries to develop advances driving assistance system.that are based on sensor technologies such as radar laser cameras and GPS.it is a vehicle to vehcile and vehile to infrastructure designing.Prescan also implemented in Matlab/simulink.AutoDrieve1 and AutoDrive2 can easily be integrated in prescan.
AutoDrive1 and AutoDrive to include TIS(technology independent sensor).which identify the speed and position of objects and a camera.The perception layers recieves the data images and a camera and consisit among others tracking algorithams to predict the future trajectory of mobile objects and machine learning components that is based on support vector machine to detect and classify the objects.
AutoDrive1 and AutoDrive2 include test case suites with nine and 7 system level test cases.The test suite for AutoDrive1 has four failing test cases,while AutoDribve2 has two.Each cases for both AutoDrives violets saftey requirements.Each test case for AutoDrive executes respective ADS features for 1200 simulation steps.These two system level tests have been designed manually by developers to achieve high structural coverage on the code of integration rules.Time for AutoDrive1 test suite execution is 20min and for AutoDrive2 its 30min. Each test suite contains one passing test case that exercise five ADS features.

## Baseline Methods and Parameters:
In this section we describe our base line methods of random search with mutations and genetic programming and parameters used in our expriments.