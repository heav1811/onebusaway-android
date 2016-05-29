
**Faculdade de Ciências da Universidade do Porto**

- Artur Nogueira 201308142

- Simon Afonso 201305059

- Tiago Castanheira 201207833

#OneBusAway
Official Website: [OneBusAway](http://www.onebusaway.org/)

Download Android app: [PlayStore](https://play.google.com/store/apps/details?id=com.joulespersecond.seattlebusbot)

##Introduction

OneBusAway is a free application available for several platforms which goal is to offer accurate real-time information for public transports.

It contains a browsable map in order to make routes planning easily.

The notification system allows the user to be constantly reminded of nearby stops and/or transports.

It is still a project in development with several collaborators with the willing to make it a worth using app.

##Architecture Overview

* Client-Server architecture;
* Back-end server serves data throughout multiple transit agencies;
* different user interfaces(Web, Phone, API's) as multiple distinct processes;

##

![arquitecture](https://github.com/OneBusAway/onebusaway-application-modules/wiki/ArchitectureDiagram.png)

##

The user interface services are separated into distinct instances for increase of performance and reliability. Each instance can get data from different agencies, even when one of them is offline.

The data is organized into an optimited graph to support faster trips of information and respond faster to operations. 

Distinct agencies get updates independently from each other. Changing data of an agency(stop) doesn't require to process all the data from the other agencies. Therefore, this partitioned scheme decreases the time needed in processing. It is essencial when working on relatively large amount of information.

##

The user interface services each get an instance of TransitDataService interface which is implemented by federation module. It is responsible for:

    schedule computation;
    real-time arrival handling;
    trip-planning.

## Logical View

![Logical View](https://github.com/heav1811/onebusaway-android/blob/master/ASSO-docs/PackageView.png?raw=true)

App: Class package that starts the init process and loads the elements.

Maps: Class package that manages the Google Maps database.

Tripservice: Class package responsible for managing the notification and scheduler tasks.

View: Class package that displays views such as Distance to Stops, Real Time Indicators and the arrow pointers.

UI: User interface class package that controls the information showed to the user.

Util: Set of utilities such as preference settings, region and location options and math functions.

Region: Class package that contains the regions database and an interface for it's managing.

Mook: Class of objects used in tests to simulate running the application.

Provider: Class package that establishes contracts between the clients and the ObaProvider and sets the user's own local database.

Adapter: Class used to test functionalities and find bugs.

IO: Most important class package responsible for setting the connection between the users and the servers and handling requests as well as managing the backup system.


Here is a more detailed view of some aspects of logical view!

![I Dont Even Know](https://github.com/tuianog/onebusaway-android/blob/master/ASSO-docs/development_view.png?raw=true)

Mock simulation: 

![Mock_simulation_view](https://github.com/tuianog/onebusaway-android/blob/master/ASSO-docs/development_mock_simulation.png?raw=true)


## Development View

![Development View](https://github.com/heav1811/onebusaway-android/blob/master/ASSO-docs/implementation_view_v1.png?raw=true)

This views allows us to observe the decomposition of the system from a programmer's point of view. With it we can understand what are the main components of our study project. As we can see in the picture above since it's an client server application we decided to featured the Server, which has the in real time informaction about the routes or stops, the api that gets that information, the Google Maps since it's an Android App and the main application itself. We represented the Agency Data as a component as well. 


## Process View

![Process View](https://github.com/heav1811/onebusaway-android/blob/master/ASSO-docs/process_view.png?raw=true)
The process view deals with the dynamic aspects of the system, explains the system processes and how they communicate. Since you already know that we have an application this view tells you what it does and what you can do. Here you can understand the core functionalities of the project.


## Physical View

![Physical View](https://github.com/heav1811/onebusaway-android/blob/master/ASSO-docs/deployment%20.png?raw=true)


This physical depicts the system from a system engineer's point of view. It is concerned with the topology of software components on the physical layer, as well as physical connections between components. Since our project is an android aplication it can be built from various operating systems but we only tested with windows. It is built in Android Studio ( which can be installed in Linux and Mac OX, making possible to work with the 3 OS), from AS we can build it to an android-emulator to run it in the PC. Furthermore, we can also built it into any android-device from AS. 


## Case View

![Physical View](https://github.com/heav1811/onebusaway-android/blob/master/ASSO-docs/case_view.png?raw=true)