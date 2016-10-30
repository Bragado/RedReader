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
| Reddit           | Reddit.com : the online repository of all the posts presented in this app       						   |     


####Use Cases

|      |Name            | Description                                                                                                | 
| ---- | -------------- | ---------------------------------------------------------------------------------------------------------- |
| UC01 | Front Page     | As a *User* I want to be able to access the front page in order to see the trending posts in the subreddits I am subscrided to.|
| UC02 | All Subreddits	| As a *User* I want to be able to see the trending posts from all the subreddits.|
| UC03 | Sort Posts     | As a *User* I want to be able to see posts in different orders (New, Hot, Top, Rising, Controversial) so that I can find new posts.|
| UC04 | Open Posts     | As a *User* I want to be able to open every post on my app in order to read everything that is in Reddit. |
| UC05 | Youtube Player | As a *User* I want to be able to be forwarded to youtube when watching a youtube vídeo in order to not lose its features.|
| UC06 | Read Comments  | As a *User* I want to be able to read other users' comments in order to see what they think about it.|
| UC07 | Refresh        | As a *User* I want to have a refresh button in order to keep me updated.|
| UC08 | Search         | As a *User* I want to have a search field in order to find what I like the most.|
| UC09 | Categories     | As a *User* I want to have categories in order to filtrate the subreddits I like the most.|
| UC10 | Past Versions  | As a *User* I want to be able to see “past versions” [before I touched the refresh button] in order to retrieve a subreddit watched.|
| UC11 | Login          | As a *User* I want to be able to add a reddit account in order to have the same experience that a *Registered User* has.|
| UC12 | Theme          | As a *User* I want to be able to change the theme presented by the app in order to turn my experience more comfortable.|
| UC13 | Nav Bar Color  | As a *User* I want to be able to change the nav bar color in order to turn my experience more comfortable.|
| UC14 | Different Languages | As a *User* I want to be able to have different languages in order to choose the one I feel more comfortable.|
| UC15 | Posts Font Scale | As a *User* I want to be able to change the “Posts Font Scale” in order to turn my experience more comfortable	       |
| UC16 | Inbox Font Scale | As a *User* I want to be able to change the “Inbox Font Scale” in order to turn my experience more comfortable	       |
| UC17 | Thumbnails      | As a *User* I want to be able to deal with “thumbnails” in order to save bandwidth|
| UC18 | Image Viewer    | As a *User* I want to be able to change the image Viewer [when watching images] in order to see the images where I like the most 	       |
| UC19 | GIF Viewer      | As a *User* I want to be able to change the GIF Viewer [when watching GIF’s] in order to see the images where I like the most 	       |
| UC20 | Video Viewer      | As a *User* I want to be able to change the Video Viewer [when watching videos] in order to see the videos where I like the most 	       |
| UC21 | Album Viewer    | As a *User* I want to be able to change the Album Viewer [when watching albums] in order to see the images where I like the most	       |
| UC22 | Gallery Swipe Length | As a *User* I want to be able to change the Gallery Swipe Length in order to chooge the best length that matches my smartphone 	       |
| UC23 | Sorting         | As a *User* I want to be able to choose the default sort for the different things (sush as posts, comments, etc) in order to have my preferences as default 	       |
| UC24 | Post Actions    | As a *User* I want to be able to choose different actions when I fling a post left/right in order to create a shortcuts to my actions 	       |
| UC25 | Comments settings | As a *User* I want to be able to change the settings of the comments in order to turn my experience more comfortable	       |
| UC26 | Cache Storage   | As a *User* I want to be able to change the cache storage location in order full control of my application data	       |
| UC27 | Precache Images | As a *User* I want to be able to precache Images in order to increase the performance of my application	       |
| UC28 | Cache storage duration | As a *User* I want to be able to control the duration of the cache storage in order to free it 	       |
| UC29 | TOR             | As a *User* I want to be able to use TOR in order to have a better user experience       |
| UC30 | Profile         | As a *Registered User* I want to be able to see my profile in order to view comments or send messages	       |
| UC31 | Inbox           | As a *Registered User* I want to be able to see my inbox in order to respond to other registered users	       |
| UC32 | Save Posts      | As a *Registered User* I want to be able to save posts and a have a folder to them in order to watch them again later	       |
| UC33 | Upvote/Downvote | As a *Registered User* I want to be able to upvote/downvote posts in order to avaliate them	       |
| UC34 | Menus Settings  | As a *User* I want to be able to change what I see on my app’s menus in order to add/remove shortcuts 	       |
| UC35 | Upvote Folder   | As a *Registered User* I want to be able to see the post I upvoted in order to see them again	       |
| UC36 | Leave a comment | As a *Registered User* I want to be able to leave a comment in order to show what a think about a particulary post 	       |
| UC37 | Up/DownVote a Comment | As a *Registered user* I want to be able to upvote/downvote comments in order to avaliate them	       |
| UC38 | Nav Bar         | As a *User* I want to be able to have a nav bar in order to have all the shortcuts I need	       |
| UC39 | Search Comments | As a *User* I want to be able to search comments in order to re-read a comment	       |
| UC40 | Copy URL        | As a *User* I want to be able to copy comment URL in order to forward it to other users	       |
| UC41 | Split Window support | As a *User* I want to be able to have “split window support” in other to open other applications	       |
| UC42 | Hide Posts      | As a *Registered User* I want to able to hide a post in order to remove them from my feed.     |
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

####Item 1

####Item 2

####Item 3

####Item 4

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
