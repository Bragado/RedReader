## Software Design for RedReader

## Authors

* Diana Isabel Garcia Pinto
* João Henrique Poceiro Vieira de Araújo
* Luís Filipe Rodrigues Coelho
* Marisa Daniela Quintal Oliveira

---

### Table of Contents
1. [Introduction](#intro)
2. [Views](#views)    
  1. [Logical view](#logical)
  2. [Development view](#development)
  3. [Process view](#process)
  4. [Deployment view](#deployment)
3. [Architectural Patterns](#patterns) 

---

### Abstract

At this stage we will describe the software structure of RedReader, based on the source code and the project documentation, made available.
Poorly designed architectures can lead to instabilities, inability to support requirements - present or future - and difficulty in applying or managing the production environment. This is where software architecture comes in - the fundamental organization of a system, formed by its components, the relationships between them and the principles that shape its design and evolution. Our approach to RedReader architecture will be based on model 4 + 1 software architecture views. The 4 views represent the logical view, implementation view, process view and distribution view, with the additional view (+1) being the use-cases view, the diagram of which has already been presented in the last report.

---

### <a name="intro"></a> Introduction

The 4+1 View Model describes software architecture using five concurrent views. Often, software engineers wonder: *“what do we want to do”* or *“how are we going to do it”*, so they need a model that defines how they can divide the system in modules and how can they be connected with each other. These concerns divide the system in components that *“can be developed in parallel and subsequently integrated, and identify opportunities for reuse.”* In order to do that we need a specific set of concerns with the 4+1 View Model: "The logical view describes the design's object model, the process view describes the design's concurrency and synchronization aspects; the physical/deployment view describes the mapping of the software onto the hardware and shows the system's distributed aspects, and the development view describes the software's static organization in the development environment. Software designers can organize the description of their architectural decisions around these four views and then illustrate them with a few selected use cases, or scenarios, which constitute a fifth view. The architecture is partially evolved from these scenarios. The 4+1 View Model allows various stakeholders to find what they need in the software architecture. System engineers can approach it first from the physical view, then from the process view; end users, customers, and data specialists can approach it from the logical view; and project managers and software-configuration staff members can approach it from the development view."
 
This report  will be about RedReader 4+1 View Model as said before. We alert that RedReader has no documentation available or any type of document describing each package/classe implemented. There’s also no comments in the code, therefore this report can be wrong in some sections, but we did our best to avoid it.

For the logic view we will have another [file](https://github.com/Bragado/RedReader/blob/master/esofDocs/Logical%20View.md), to analyse a litle better this section. 

---

### <a name="views"></a> Views

#### <a name="logical"></a> Logical View

RedReader is an Android app so there are only four different types of app components: Activities; Services; Content providers; Broadcast receivers. RedReader uses them all. Almost every class in RedReader extends from one of these four components. The app starts with RedReader class, that extends from activity, and that’s how almost every android application starts. Then, calls another class that extends from Service (threads) and so on. So basically, what I want to say with this is that Android has important components to this project, however we are not going to study them, we take them as "granted".  

The Logic View “shows the logical packages and their relationships”. As said before, we have another [file](https://github.com/Bragado/RedReader/blob/master/esofDocs/Logical%20View.md) describing with more detail every package therefore, in this section, the following diagram shows an overview of all packages presented in RedReader.

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/logicalView.png" alt="LogicalView"/>
</p>

---

#### <a name="development"></a> Development View
We can not analyse every single aspect in RedReader and the following diagram only focus on how the RedReader presents data to users.
First of all we want to alert to the fact that Reddit and Android are not components from our project. Android is not considered a component because, as said before, even knowing  that all application relies in Android components, they are taken for granted. However, we still add the component in this diagram, only to show that this is only possible thanks to Android components. The same happens with Reddit. Reddit is not a component in our project, however, it offers tools to download the information in their database.

But, how does it work?
Reddit offers tools/methods to download information and that's why RedReader needs a component to manage that information (packages described before such as  "IO"). To retrieve that information RedReader needs a "bridge", that is, a component called Network ( package jsonwrap for example) that can offer an  interface to access Reddit so that the previous component can work.
Then, RedReader needs to manage all the data retrieved from Reddit database, that's why we need a General Manager ( such are packages reddit and common ). After everything is downloaded the information needs to be presented and that's what RedReaderApplication offers, a user Interface.
The component cache is always running in a different Thread.  That's the scenario presented in the following diagram.

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/implement%20view.PNG" alt="LogicalView"/>
</p>

---
#### <a name="process"></a> Process View
The next two diagrams demonstrate two distinct scenarios.
We take this opportunity to remind that this is just an overview of what really happens in RedReader.
The application starts and two threads are created (in both diagrams). The first thread to be created, dominated by "Cache", is responsible to control the cache and pre-cache of application data. The second thread is the information manager.

Focusing now on the first diagram, after the creation of the second thread, the activity corresponding to the current state is updated. After a user command (eg, selection of a category of posts), RedditChangeData is warned and requests the RedditManager to obtain the information desired by the user. RedditManager, uses the Network to retrieve Reddit's information and returns it to RedditChangeData. This warns the Cache about the operation and returns to update "Activities", in order to demonstrate what the user asked for. This process is repeated until the user wants to exit the application, except when the information is already cached.

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/case1.PNG" alt="LogicalView"/>
</p>
<p>
</p>

The second diagram depicts the previous exception, the functionality of the pre-cache in terms of performance.

The second diagram reads as follows:
* RedReader starts and the two threads are created
* The Initial Activity is displayed to the user
* The user chooses a category
* RedditManager will fetch the information to reddit, and meanwhile signal the Cache
* RedditManager returns the information and updates the Activity that is presented to the user
* When the user decides to open a post, RedditManager does not need to go to Reddit once it has been cached, thus updating the user's activity immediately

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/case2.PNG" alt="LogicalView"/>
</p>


---
#### <a name="deployment"></a> Deployment View

The UML distribution diagram models the physical distribution of artifacts in nodes.

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/deploymentView.png" alt="deploymentView"/>
</p>

This diagram shows the organization of the hardware (nodes and their connections, if any) in the RedReader project system.
We only have one node, the User's Device that corresponds to the user's hardware, that is, your computer or smartphone with the RedReader application.

---

### <a name="patterns"></a> Architectural Patterns

It’s hard to identify a design pattern in RedReader. The Model View Controller seems to be a nice approach to any android application, once, the core operation of android apps is to obtain information from a data store and update the UI.

Let’s now analyse Android and what MVC stands for:

MVC Pattern stands for Model-View-Controller Pattern. This pattern is used to separate application's concerns.
* **Model** - Model represents an object or JAVA POJO carrying data. It can also have logic to update controller if its data changes.
* **View** - View represents the visualization of the data that model contains.
* **Controller** - Controller acts on both model and view. It controls the data flow into model object and updates the view whenever data changes. It keeps view and model separate.

Android overview:
* **Activity** – represents the user interface class, usually packaged together to form the UI components of the application
* **Service** – allow tasks to be executed in background threads without affecting UI components
* **Content Provider** – enable data to be stored within the application
* **Broadcast Receiver** – responds to announcements from the system and provides notifications to the user.

This means, Android follows what MVC stands for. And this is exactly what we see in RedReader. RedReader uses Activities to represent the user interce, uses Services to access Reddit and start all the necessary threads, uses Content Provider to store the information and the broadcast receiver to provide notifications to the user.  

It seems that MVC patterns fits well with our application however, if we look close things are different. And here is an example:

The is defined UI layout of the Activity in the XML file and implement the functionality and behavior in the Java file. When we use a button, for example, the button is defined as XML element in the layout file to instantiate the button and its behavior. The handling of the behavior of the widget in response to user actions is also implemented in the same file. The button’s attributes from XML layout are access while implementing its functionality and this MVC pattern (View and Controller are not separated).

Doing some research we found that MVC can be used in android apps using an Observer pattern within MVC. It does not seem to be case in this project, that’s why we said previously that “It’s hard to say”.

