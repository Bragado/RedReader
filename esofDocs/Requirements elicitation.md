## High Level Requirement Specification for RedReader

## Authors

* Diana Isabel Garcia Pinto
* João Henrique Poceiro Vieira de Araújo
* Luís Filipe Rodrigues Coelho
* Marisa Daniela Quintal Oliveira

---

### Table of Contents
1. [Introduction](#)
  1. [Context](#)
  2. [Purpose and Scope](#)
2. [Overall Description and Use Cases](#)    
4. [Non-functional Requirements](#)
 1. [item 1](#)  
 2. [item 2](#)  
 3. [item 3](#)  
5. [Functional Requirements](#)  
 1. [item 1](#)  
 2. [item 2](#)  
 3. [item 3](#)  
6. [Domain Model](#)  

---

###Introduction


####Context

####Purpose and Scope

---

###Overall Description and Use Cases

####Stakeholders
<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/stakeholders.PNG" alt="Project's Stakeholders"/>
</p>

| Identifier       | Description                                                                                               |         
| ---------------- | --------------------------------------------------------------------------------------------------------- | 
| User             | Unregistered user: can view the post and change the application settings                                  | 
| Registered User  | Authenticated user that has an account on the system and a profile. Can comment, vote and send messages.  |  
| Reddit           | Reddit.com : the online repository of all the posts presented in this app       						   |     


####User Cases

|      |Name            | Description                                                                                                | 
| ---- | -------------- | ---------------------------------------------------------------------------------------------------------- |
| UC01 | Front Page     | As a *User* I wanna be able to acess the front page in order to see the trending subreddits	                 |
| UC02 | Sort Posts     | As a *User* I wanna be able to see subreddits in different orders (new, hot, top, rising, controversial) so that I can find new subreddits.|
| UC03 | Open Posts     | As a *User* I wanna be able to open every subreddit on my app in order to read everything that is in reddit. |
| UC04 | Youtube Player | As a *User* I wanna be able to be forward to youtube when watching a youtube vídeo in order to not lose their features|
| UC05 | Read Comments  | As a *User* I wanna be able to read others users comments in order to see what they think about it	       |
| UC06 | Refresh        | As a *User* I wanna have a refresh button in order to keep me updated	       |
| UC07 | Search         | As a *User* I wanna have a search field in order to find what I like the most	       |
| UC08 | Categories     | As a *User* I wanna have categories in order to filtrate the subreddits I like the most	       |
| UC09 | Past Versions  | As a *User* I wanna be able to see “past versions” [before I touched the refresh button] in order to retrieve a subreddit watched	       |
| UC10 | Login          | As a *User* I wanna be able to add a reddit account in order to have the same experience that a registered user has  	       |
| UC11 | Theme          | As a *User* I wanna be able to change the theme presented by the app in order to turn my experience more comfortable	       |
| UC12 | Nav Bar Color  | As a *User* I wanna be able to change the nav bar color in order to turn my experience more comfortable	       |
| UC13 | Different Languages | As a *User* I wanna be able to have different languages in order to choose the one I feel more comfortable  	       |
| UC14 | Posts Font Scale | As a *User* I wanna be able to change the “Posts Font Scale” in order to turn my experience more comfortable	       |
| UC15 | Inbox Font Scale | As a *User* I wanna be able to change the “Inbox Font Scale” in order to turn my experience more comfortable	       |
| UC16 | Thumbnails      | As a *User* I wanna be able to deal with “thumbnails” in order to save bandwidth|
| UC17 | Image Viewer    | As a *User* I wanna be able to change the image Viewer [when watching images] in order to see the images where I like the most 	       |
| UC18 | GIF Viewer      | As a *User* I wanna be able to change the GIF Viewer [when watching GIF’s] in order to see the images where I like the most 	       |
| UC19 | Album Viewer    | As a *User* I wanna be able to change the Album Viewer [when watching albuns] in order to see the images where I like the most	       |
| UC20 | Gallery Swipe Length | As a *User* I wanna be able to change the Gallery Swipe Length in order to chooge the best length that matches my smartphone 	       |
| UC21 | Sorting         | As a *User* I wanna be able to choose the default sort for the different things (sush as posts, comments, etc) in order to have my preferences as default 	       |
| UC22 | Post Actions    | As a *User* I wanna be able to choose different actions when I fling a post left/right in order to create a shortcuts to my actions 	       |
| UC23 | Comments settings | As a *User* I wanna be able to change the settings of the comments in order to turn my experience more comfortable	       |
| UC24 | Cache Storage   | As a *User* I wanna be able to change the cache storage location in order full control of my application data	       |
| UC25 | Precache Images | As a *User* I wanna be able to precache Images in order to increase the performance of my application	       |
| UC26 | Cache storage duration | As a *User* I wanna be able to control the duration of the cache storage in order to free it 	       |
| UC27 | TOR             | As a *User* I wanna be able to use TOR in order to have a better user experience       |
| UC28 | Profile         | As a *Registered User* I wanna be able to see my profile in order to view comments or send messages	       |
| UC29 | Inbox           | As a *Registered User* I wanna be able to see my inbox in order to respond to other registered users	       |
| UC30 | Save Posts      | As a *Registered User* I wanna be able to save posts and a have a folder to them in order to watch them again later	       |
| UC31 | Upvote/Downvote | As a *Registered User* I wanna be able to upvote/downvote posts in order to avaliate them	       |
| UC32 | Menus Settings  | As a *User* I wanna be able to change what I see on my app’s menus in order to add/remove shortcuts 	       |
| UC33 | Upvote Folder   | As a *Registered User* I wanna be able to see the post I upvoted in order to see them again	       |
| UC34 | Leave a comment | As a *Registered User* I wanna be able to leave a comment in order to show what a think about a particulary post 	       |
| UC35 | Up/DownVote a Comment | As a *Registered user* I wanna be able to upvote/downvote comments in order to avaliate them	       |
| UC36 | Nav Bar         | As a *User* I wanna be able to have a nav bar in order to have all the shortcuts I need	       |
| UC37 | Search Comments | As a *User* I wanna be able to search comments in order to re-read a comment	       |
| UC38 | Copy URL        | As a *User* I wanna be able to copy comment URL in order to forward it to other users	       |
| UC39 | Split Window support | As a *User* I wanna be able to have “split window support” in other to open other applications	       |
| UC40 |      | 	       |
| UC41 |      | 	       |
| UC42 |      | 	       |
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

###Non-functional Requirements

####Item 1

####Item 2

####Item 3

####Item 4

---

###Domain Model
