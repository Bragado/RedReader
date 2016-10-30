## High Level Requirement Specification for RedReader

## Authors

* Diana Isabel Garcia Pinto
* João Henrique Poceiro Vieira de Araújo
* Luís Filipe Rodrigues Coelho
* Marisa Daniela Quintal Oliveira

---

### Table of Contents
1. [Introduction](#intro)
  1. [Context](#context)
  2. [Purpose and Scope](#PS)
  3. [Requirements Elicitation](#reqEli)
2. [Overall Description and Use Cases](#useCase)    
4. [Non-functional Requirements](#NFReq)
5. [Functional Requirements](#FReq)  
6. [Domain Model](#dm)  

---

### <a name="intro"></a> Introduction


#### <a name="context"></a> Context
RedReader is an open source mobile app available for Android and iOS devices. Described as an “unofficial, open source client for reddit”, it already has over 50.000 downloads on the PlayStore.
#### <a name="PS"></a> Purpose and Scope
This document intends to represent a high level view of RedReader, through its features, interfaces and some non-functional requirements considered essential. Some of the content discuss in this report was studied with more detail on [previous report](https://github.com/Bragado/RedReader/blob/master/esofDocs/Model%20Process.md). 
#### <a name="reqEli"></a> Requirements Elicitation
As said in [previous report](https://github.com/Bragado/RedReader/blob/master/esofDocs/Model%20Process.md), RedReader does not have a specific model for requirements elicitation, so each release pretty much works like this:
* People continuously suggest new features.
* The developer pick out the most popular/useful ones to go into the release, and implements them over the course of a few months.
* The code gets merged in immediately (continuous integration), and an alpha version gets built for nearly every commit.
* If other contributors submit pull requests during that time, the main developer reviews them and they get merged in.
* Once all that is promised is done, he test all the major functionalities on various platforms.
* Then, after a few days (to wait for alpha bug reports to come in) there is a release.

---

### <a name="useCase"></a> Overall Description and Use Cases

####Stakeholders
<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/stakeholders3.PNG" alt="Project's Stakeholders"/>
</p>

| Identifier       | Description                                                                                               |         
| ---------------- | --------------------------------------------------------------------------------------------------------- | 
| User             | Unregistered user: can view the post and change the application settings                                  | 
| Registered User  | Authenticated user that has an account on the system and a profile. Can comment, vote and send messages.  |  


####Use Cases

|      |Name            | Description                                                                                                | 
| ---- | -------------- | ---------------------------------------------------------------------------------------------------------- |
| UC01 | Front Page     | As a *User* I want to be able to access the front page in order to see the trending posts in the subreddits I am subscrided to.|
| UC02 | All Subreddits	| As a *User* I want to be able to see the trending posts from all the subreddits.|
| UC03 | Sort Posts     | As a *User* I want to be able to see posts in different orders (New, Hot, Top, Rising, Controversial) so that I can find new posts.|
| UC04 | Open Posts     | As a *User* I want to be able to open every post on my app in order to read everything that is in Reddit. |
| UC05 | Youtube Player | As a *User* I want to be able to be forwarded to youtube when watching a youtube vídeo in order not to lose its features.|
| UC06 | Read Comments  | As a *User* I want to be able to read other users' comments in order to see what they think about a certain post.|
| UC07 | Refresh        | As a *User* I want to have a refresh button in order to keep me updated.|
| UC08 | Search         | As a *User* I want to have a search field in order to find what I like the most.|
| UC09 | Categories     | As a *User* I want to have categories in order to filter the subreddits I like the most.|
| UC10 | Past Versions  | As a *User* I want to be able to see “past versions” [before I touched the refresh button] in order to retrieve cached subreddit versions.|
| UC11 | Login          | As a *User* I want to be able to add a Reddit account in order to have the same experience that a *Registered User* has.|
| UC12 | Theme          | As a *User* I want to be able to change the theme presented by the app in order to make my experience more enjoyable.|
| UC13 | Nav Bar Color  | As a *User* I want to be able to change the navigation bar color in order to make my experience more comfortable.|
| UC14 | Different Languages | As a *User* I want to be able to have different languages in order to choose the one I feel more comfortable with.|
| UC15 | Posts Font Scale | As a *User* I want to be able to change the “Posts Font Scale” in order to make my experience more comfortable.|
| UC16 | Inbox Font Scale | As a *User* I want to be able to change the “Inbox Font Scale” in order to make my experience more comfortable.|
| UC17 | Thumbnails      | As a *User* I want to be able to enable/disable “thumbnails” in order to save bandwidth.|
| UC18 | Image Viewer    | As a *User* I want to be able to change the Image Viewer [when watching images] in order to see the images where I like the most.|
| UC19 | GIF Viewer      | As a *User* I want to be able to change the GIF Viewer [when watching GIF’s] in order to see the images where I like the most.|
| UC20 | Video Viewer      | As a *User* I want to be able to change the Video Viewer [when watching videos] in order to see the videos where I like the most.|
| UC21 | Album Viewer    | As a *User* I want to be able to change the Album Viewer [when watching albums] in order to see the images where I like the most.|
| UC22 | Gallery Swipe Length | As a *User* I want to be able to change the Gallery Swipe Length in order to choose the best length that matches my smartphone.|
| UC23 | Sorting         | As a *User* I want to be able to choose the default sort for the different things (sush as posts, comments, etc) in order to have my preferences as default.|
| UC24 | Post Actions    | As a *User* I want to be able to choose different actions when I fling a post left/right in order to create shortcuts for my actions.|
| UC25 | Comments settings | As a *User* I want to be able to change the settings of the comments in order to make my experience more comfortable.|
| UC26 | Cache Storage   | As a *User* I want to be able to change the cache storage location in order to have full control over my application data.|
| UC27 | Precache Images | As a *User* I want to be able to precache Images in order to increase the performance of my application.|
| UC28 | Cache storage duration | As a *User* I want to be able to change the duration of the cache storage in order to control the memory used.|
| UC29 | TOR             | As a *User* I want to be able to use TOR in order to protect my privacy.|
| UC30 | Profile         | As a *Registered User* I want to be able to see my profile in order to view comments or send messages.|
| UC31 | Inbox           | As a *Registered User* I want to be able to see my inbox in order to respond to other registered users.|
| UC32 | Save Posts      | As a *Registered User* I want to be able to save posts and have a folder to them in order to view them again later.|
| UC33 | Upvote/Downvote Posts | As a *Registered User* I want to be able to upvote/downvote posts in order to rate them.|
| UC34 | Menu Settings  | As a *User* I want to be able to change what I see on my app’s menus in order to add/remove shortcuts.|
| UC35 | Upvote Folder   | As a *Registered User* I want to be able to see the posts I upvoted in order to view them again later.|
| UC36 | Leave a comment | As a *Registered User* I want to be able to leave a comment in order to show what I think about a particular post.|
| UC37 | Upvote/Downvote Comments | As a *Registered user* I want to be able to upvote/downvote comments in order to rate them.|
| UC38 | Nav Bar         | As a *User* I want to be able to have a navigation bar in order to have all the shortcuts I need.|
| UC39 | Search Comments | As a *User* I want to be able to search comments in order to find a specific comment.|
| UC40 | Copy URL        | As a *User* I want to be able to copy a comment's URL in order to forward it to other users.|
| UC41 | Split Window support | As a *User* I want to be able to have “split window support” in other to open other applications.|
| UC42 | Hide Posts      | As a *Registered User* I want to able to hide a post in order to remove it from my feed.|
| UC43 |      | 	       |
| UC44 |      | 	       |
| UC45 |      | 	       |
| UC46 |      | 	       |
| UC47 |      | 	       |
| UC48 |      | 	       |
| UC49 |      | 	       |
| UC50 |      | 	       |

####Use Case Diagram
<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/use%20case%20diagram.PNG" alt="Use Case Diagram"/>
</p>



---

### <a name="NFReq"></a> Non-functional Requirements

####Software & Hardware 
* The app should be compatible with all Android devices with a minimum version of 4.0
* The system should be developed in Java
 
####Maintainability
* The code should be well structured in order to appeal to contributions from the community
 
####Security & Privacy
* The system should keep users privacy, the user is the one who decides if RedReader should access or not his private information on Reddit
 
####Performance
* The system should refresh in no more than 2.5 seconds
* The posts shoud be open in no more than 3 seconds
* Images/comments should be open instantly (using techniques such as pre-caching)

####Availability
* The system should be available all the time [as long as Reddit is online]
* The system should be free and ads free for anyone who wants to use it

####Portability
* The system should embrace the different features of the different smartphones (such us LG spliting window)

---

### <a name="FReq"></a> Functional Requirements
The following functional requirements describes the major services that are available for RedReader's users
* Free and Open Source - no ads/tracking.
* Swipe posts and comments left and right to perform customizable actions, such as upvote/downvote, or save/hide.
* Advanced cache management - automatically stores past versions of posts and comments.
* Support for multiple accounts.
* Two-column tablet mode 
* Image precaching 
* Built in image viewer, and GIF player.
* Support for imgur albums and gifv files
* Compression
* Night mode 
* Translations for some languages

One of the most important functional requirements that only exists for a *registered user* is the ability to make new posts or post comments.

---
### <a name="dm"></a> Domain Model

The domain model is a representation of meaningful real-world concepts pertinent to the domain that need to be modeled in software. 

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/DomainModel.png" alt="Domain Model"/>
</p>


### <a name="conclusions"></a> Conclusions


#### Requirements specification

After our analise, there's no specific document that shows the next requirements that are importante to redReader. In a more organized situation, this should be the time that we presented a formal document with all the requirements that should come up next. However, in a project like redreader there’s a huge diversity of new requirements therefore, a document like the one we refered does not make sence. Our suggestion is to separete the requirements in groups and create long/short term  objectives to implemente them. Every new feature required could be added to those groups.

#### Requirements validation

The process used in RedReader is different with what we are used to see in the software market. In this project, like most of open source projects, skateholders suggest new features but it’s the main contributor who decides which ones should be implemented.  The main contributor accepts most of all the new suggestions and that can create a problem: there’s a huge number of requirements to be implemented and the easiest ones are the first to be implemented. With our previous suggestions it would be better to prioritize the requirements.<br>
Red Reader uses [Travis CI](https://travis-ci.org/QuantumBadger/RedReader) in order to add, without conflitos, code from others contributors. The “passing” of the requirements on the tests of Travis means that the requirement will be accepted, even if it was not a priority. That will create a desorder in the requirements specification but is something that has to be done in order to embrace contributions.<br>
GitHub offers tags for the issues in order to classificate them in different categories, contributing to a better organization, something that could be more explored in this project. In our opinion, a better organization and tagging of the issues will facilitate a better validation process and prioritization.

#### Overall conclusions

The process of requirements specification and validation of this project is far from perfect. There’s so much to do in order to improve. Before, we referenced some cautions that should be taking in care in order to improve it now, we will describe some problems of not doing it: The perfect example of a problema due to the lack of organization and priorities is the search field. Users ask for it during 2 years and now (that is implemented) users often create issues about the search field because they think it was not implemented and that’s due to the lack of organization. The project has a poor usability when new features come out and this is an example of that. The search field is really importante on projects like this one and should be one of the “pop out” features. The same happens with the feature of creating new posts. To create new posts in redreader users have to open a post, access to the settings and choose to create a new post. To leave a comment, users have to press a comment for a second and choose to reply. This is a bad user interface and at this moment, changes will be difficult and would consume a huge amount of effort.<br> 
Therefore, we conclude that, a better requirements elicitation should be desenvolved in order to facilitate the developers work. Requirements should be grouped and receive a priority, not a priority based on how easy it is to implemente but, a priority based on how much that group of requiriments contribute to a “long term” objective.
