# An Ontological Architecture for Principled and Automated System of Systems Composition

# Authors:

## Abdessalam Elhabbash, 

![Image](./image9.jpg)

## Vatsala Nundloll, 

## Yehia Elkhatib,
![Image](./image8.jpg) 

## Gordon Blair, 

## Vicent Sanz Marco

# Confrence Name
## ICSE 2020 Program
***

[Confrence Link](https://2020.icse-conferences.org/program/program-icse-2020)

>Venue:Tue 30 Jun 2020 14:00 - 14:05 at SEAMS - Session 3: Composition, Control and Trustworthiness 
>>Chair(s): Danny Weyns


[Preprint Link](https://yelkhatib.github.io/papers/Elhabbash2020Ontological.pdf)

[Medial Link](https://youtu.be/jp5djzHGtiQ)

# Abstract:

A dsitributed system is continuously evolved in changes according to enviroment so we adapt system of systems to understand software.This paper presents a conceptual methodology for selecting existing systems to form candidate systems of systems (SoS) and selecting the preferred candidate SoS to provide a new capability. This methodology begins with SoS acquisition and mission requirements and selects the preferred SoS in six steps. Decision factors used for this purpose are selected based on their importance in providing and sustaining the required SoS capability. A new index of priority is introduced and utilized in this methodology to compare candidate systems, in terms of their assigned mission priority, with respect to the SoS mission priority, as well as their contribution to the SoS mission.  In the last decades, the use of ontologies in information systems has become more and more popular in various fields, such as web technologies, database integration, multi agent systems, natural language processing, etc. Artificial intelligent researchers have initially borrowed the word “ontology” from Philosophy, then the word spread in many scientific domain and ontologies are now used in several developments.

# Introduction:
Computer system are evovled in the basic pictures of connected PCS to inter connected PCS of heterogenous system. .Each of these systems contains a set of heterogeneous components that implement diverse functions communicating using different protocols.Further more,these various systems often need to interact and collaborate to achieve their goals.For example,isolated rescue teams need to opportunistically compose and access each others services(e.g.,datalook-up)to exchange information; deployed environmental IoT systems process their data on a micro cloud in their vicinity and off load certain processing to the cloud when needed; etc. In this sense, larger systems are constructed through the interaction of smaller ones,a practice known as System of Systems (SoS) composition.Heterogenity and scale pose significant challenges to SoS construction. Developers need knowldege to construct SoS. A number sub systems combined to make a system of system it is a complex system. SoSs are typically deployed in environments where context changes.This is where the need arises to veerfromastrict work flow path that has been defined at design time,and form a more complex system in order to maintain the intended abstract behavior or to be able to provide new behavior that is only possible through uniting with other systems in the new context.Such examples include disaster recovery,adaptive IoT applications,volunteer and crowd computing, military defense operations, and other forms of cyber physical systems.Further more,the development of SoS is dynamic in nature.This is grounded in the knowledge that systems are persistent and long-living. As such, their objectives and functionalities evolve over time as they are constantly added,modified,or removed at different time scales.This might also predicate changes in architectural and functional dependencies. An example of ontology is when a physicist establishes different categories to divide existing things into in order to better understand those things and how they fit together in the broader world. ... Whereas the World Wide Web links Web pages together, the Semantic Web links the data on the Web that are related. In order to achieve this objective,there is a need for semantics to comprehensively describe the system structure,capturing the information required for dynamically composing systems such as those relating to communication(e.g.,unique identifiers),service discovery,quality of service,physical properties(e.g.,powerlevel and location),environmental properties,etc.We refer to this comprehensive structure description of a system as a holon. A holon is constantly modified to reflect the system structure and to contain any new or modified information,and then published to aid discovery and reasoning about composition.When holons compose,they form a new holon that represents the SoS.This newlyc onstructed holon will now have its own specification,which is published so that thee system can further compose with other SoSs and soon. The service composition supported by SOA is mainly functionality based composition.How ever,SoS composition is wider than this,as it also requires knowledge about system properties and context to reason about the composition.Second,services in SOA are assumed to be published in a repository that an orchestrator can consult to select services from.This assumption is not valid in the general SoS context which is fully distributed.Third,SOA-based SoS developers are expected to know alot about individual systems,or invest significant time learning them.   Developers are required to acquire knowledge about the APIs and properties of the elementary systems they need to compose.Then, they need to leverage that knowledge to design and implement the SoS,and finally deploy it.This requires the developer to focus on the elementary systems instead of the whole SoS.

# Problem Space and Related Work:
This paper presents an approach to system-of-systems engineering for product development with the use of ontology. A proposed method for building as well as using ontology to generate and explore system-of-systems design spaces based on identified system-of-system needs is presented. The method is largely built to cover the first levels of related work, where a process for system of systems in the context of product development is introduced. Within this work, it is shown that scenarios for a system-of-systems can be used to identify needs and subsequently the system-of-systems capabilities that fulfils them. The allocation of capabilities to possible constituent systems is used to show the available design space. The proposed method of this paper therefore addresses these initial challenges and provides a framework for approaching the system-of-systems design space creation using ontology. A case study is used to test the method on a fictitious search and rescue scenario based on available resources and information from the Swedish Maritime Administration. The case study shows that a representation of a system-of-systems scenario can be created in an ontology using the method. The ontology provides a representation of the involved entities from the fictitious scenario and their existing relationships. Defined ontology classes containing conditions are used to represent the identified needs for the system-of-systems. The invocation of a description logic reasoner is subsequently used to classify and create an inferred ontology where the available system-of-systems solutions are represented as sub-classes and individuals of the defined classes representing the needs. Finally, several classes representing different possible system-of-systems needs are used to explore the available design space and to identify the most persistent solutions of the case study.

# RESEARCH STRATEGY:

Based on the above, our ultimate goal is to shift the developers’ focus from learning the internals of elementary systems to thinking at the level of the SoS. As shown in Fig. 1, holons allow developers to focus on defining high-level workflows of the SoS. The elementary systems need to autonomously discover each other and compose to serve the requests.The achievement of this goal requires (1) a comprehensive description of the atomic systems (their services, properties, and context) that enable autonomous composition between systems;

and (2) an architecture the exploits such descriptions and supports SoS composition and adaptation.

# 4 THE HOLONIC LIFE CYCLE: 
A holon starts as an atomic one then might evolve to being composite. An atomic holon represents a single system that provides one or more functionalities.A composite holon includes functionalities provided by a number of systems interacting with eachother either directly or through others.In order for holons to compose, atomic holons need to be comprehensively specified by the system developer.After that,the system will be dynamically constructed as the holons iterate in their lifecycle.The four stages of a holon’s life cycle:




