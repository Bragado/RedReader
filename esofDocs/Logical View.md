# Logical View

## Authors

* Diana Isabel Garcia Pinto
* João Henrique Poceiro Vieira de Araújo
* Luís Filipe Rodrigues Coelho
* Marisa Daniela Quintal Oliveira

---
### Introduction

Android apps are written in the Java programming language. 
App components are the essential building blocks of an Android app. Each component is an entry point through which the system or a user can enter your app. Some components depend on others.

There are four different types of app components:

* Activities.
* Services.
* Content providers.
* Broadcast receivers.

Every android aplication starts with a class that extends from Activity and to use the features of our smartphones android already has libraries or components to do it, we, developers, only have to extend our classes from this components/libraries. This said, there will be lots of classes in RedReader that extend from android classes or java classes (android also uses jdk).
The following logic view diagrams ignore the fact that almost every class extend from an android class. 

---

### Account

The following package contains the necessary classes that RedReader uses to access user's accounts. One of them, RedditAccountManager, extends SQLiteOpenHelper, a library made in android to "emulate" sql database.

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/Account.PNG" alt="Account"/>
</p>
---

### Activities

An activity is the entry point for interacting with the user. It represents a single screen with a user interface. Applications can have a huge amount of activities and that's this package has so many classes. Every classe extends from Activity or extends from a class that extends from Activity.

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/Activities.PNG" alt="Activities"/>
</p>
---

### Adapters

An Adapter object acts as a bridge between an AdapterView and the underlying data for that view. The Adapter provides access to the data items. The Adapter is also responsible for making a View for each item in the data set. 

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/adapters.PNG" alt="Adapters"/>
</p>
---

### Cache

This package is responsable for cache the app's resources. Rather than store it persistently, it opens a File that represents the internal directory where RedReader application should save temporary cache files.

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/cache.PNG" alt="Cache"/>
</p>
---

### Common

This package almost doesn't need apresentation, it implements common actions for the application.

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/common.PNG" alt="Common"/>
</p>
---

### Fragments

A Fragment represents a behavior or a portion of user interface in an Activity. We can combine multiple fragments in a single activity to build a multi-pane UI and reuse a fragment in multiple activities. Basically, instead of creating one activity for each "page" to show to the user, we create fragments that can be reuse. This package contains all the fragments of RedReader

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/fragments.PNG" alt="Fragments"/>
</p>
---

### Http

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/http.PNG" alt="Http"/>
</p>
---

### Image

This package contains libraries and methods to improve the quality and performance of RedReader when dealing with images/GIF's/video.

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/image.PNG" alt="Image"/>
</p>
---

### Io

This package contains methods to manage reddit's information

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/io.PNG" alt="io"/>
</p>
---

### Jsonwrap

This package contains all the necessary  methods to deal with json, required by reddit

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/jsonwraper.PNG" alt="Jsonwraper"/>
</p>
---

### ListingControllers

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/listingcontrollers.PNG" alt="ListingControllers"/>
</p>
---

### Receivers

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/receivers.PNG" alt="Receivers"/>
</p>
---

### Reddit

This package manages all the data given by reddit

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/reddit.PNG" alt="Reddit"/>
</p>
---

### VierHolders

Using a background thread ("worker thread") removes strain from the main thread so it can focus on drawing the UI. In other words, it makes ListView Scrolling Smooth

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/viewholders.PNG" alt="ViewHolders"/>
</p>
---

### Views

"This class (package in this case) represents the basic building block for user interface components. A View occupies a rectangular area on the screen and is responsible for drawing and event handling." 

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/views.PNG" alt="Views"/>
</p>


