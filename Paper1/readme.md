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
for example a pedestarian detected behind a car the ttc time to collision between objects and speed of both pedesterian and car should be measured if both are in same speed than thr dist(p,c) denotes the distance between car and pedistaraian p for pedistarian and c for car.dist(c,sign) denotes the distance between car and traffic sign.

