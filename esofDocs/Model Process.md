# Report 1 - ESOF

## Authors

* Diana Isabel Garcia Pinto
* João Henrique Poceiro Vieira de Araújo
* Luís Filipe Rodrigues Coelho
* Marisa Daniela Quintal Oliveira

---
### Abstract
In the context of the subject *Software Engineering* we intend to analyze the software processes used by the contributors of RedReader.
Regarding the software process we will be focusing on how the different typical phases of the process model evolved and how it was handled by the developer(s) followed by an analysis of which models best fit the project.

---

###Introduction
RedReader is an open source mobile app available for Android and iOS devices. Described as an “unofficial, open source client for reddit”, it already has over 50.000 downloads on the PlayStore. Initially released in 2013, it has come a long way until the current version available, 1.9.6. The main features are:
*	Free and Open Source Software - no ads/tracking.
*	Lightweight and fast
*	Downloads are compressed to save bandwidth.
*	Support for multiple accounts.
*	Several themes such as Night mode (i.e. dark theme) and Holo
*	Swipe posts left and right to perform customisable actions, such as upvote/downvote, or save/hide.
*	Advanced cache management - automatically stores past versions of posts and comments.
*	Two-column tablet mode (can be used on your phone, if it's big enough)
*	Image and comment precaching (optional: always, never, or Wi-Fi only).
*	Built-in image viewer, imgur album viewer, GIF player, and webm/mp4/gifv player.

---

### Project structure


#### <a name="release"></a> Release Schedule
RedReader is an open source project developed (mainly) by one contributor. Thus, when another contributor, developing new features or fixing bugs, has decided to do a pull request, the decision to merge the new feature or bug fix is left to the main contributor. There is not any particular Release Schedule. Most of the time, new versions are released when previous bugs are fixed or new features are added. The following two tables are data collected about the release of new versions.

![Service Management](img/table1.PNG)
_First Versions Released_

![Service Management](img/table2.PNG)
_Last Versions Released_ 




<p>Regarding the first table, we found that initially, at the launch of the first version of this project, several changes were released. These changes were made in the same day and in the following days (multiple times) after the initial version, leading ultimately to a more stable version due to the feedback given by the users. </p>

<p>Taking into account the second table, there were major improvements. There is no need, due to the Alpha versions, to release new versions everytime that a bug is fixed or a new feature is released. Alpha versions allow contributors to add new features without creating a new version of RedReader. Instead, they create a new Alpha version with the new feature, in order to not change the actual version of the app several times. Users are invited to test the new Alpha versions, to try the new features and report bugs. Once the Alpha version is stable and big enough to create a new version, only then is it released.</p>


####Release Branches

RedReader is an incremental development application that allows the developers to take advantage of what they have learned during the initial phases and, beyond that, receive updates in a way that the application remains attractive and innovative to the user.
It's constantly releasing new versions. In the past, the developer tried to use branches for the development of the application, but was not successful, so he opted to develop in the master branch. The suggestions given by users and application bug fixes are developed in a  continuous and gradual way in the master branch.

####Release Cycle

There doesn't seem to be a defined time of release for each new version of the application. Over the past year, the time intervals between major releases ranged from one to four months. If necessary, there may be a couple of minor updates between releases, mostly with bug fixes. Since there is only one main developer, the release cycle will ultimately depend on his code frequency and on the number of contributors actively helping during that time frame. 

After a new version has been released and to avoid having to release a new one shortly after, any new implemented functionalities can be tested in the Alpha version by users and contributors alike.

---

### Development process

RedReader is too small of a project to need a particular development model, but each release pretty much works like this:
*	People continuously suggest new features.
*	The developer pick out the most popular/useful ones to go into the release, and implements them over the course of a few months.
*	The code gets merged in immediately (continuous integration), and an alpha version gets built for nearly every commit.
*	If other contributors submit pull requests during that time, the main developer reviews them and they get merged in.
*	Once all that is promised is done, he test all the major functionalities on various platforms.
*	Then, after a few days (to wait for alpha bug reports to come in) there is a release.

However, this looks like agile software development, and we will refer to this when we focus on each point.


#### Specification and requirements elicitation

####*"People continuously suggest new features"*  (Specification and requirements elicitation)

RedReader was first [announced](https://www.reddit.com/r/Android/comments/1bskqz/ive_just_released_an_open_source_client_for/) on reddit and users started giving feedback. Some of the feedback were bug reports but most of it were suggestions about new features and that was enough to launch a new version 3 hours later.

####*"The most popular/useful ones go into the release"* 

Like shown before, RedReader has a huge support from the reddit community with new suggestions for improvement. One day after the release of the app, the developer created a [list of the suggested to-dos](https://www.reddit.com/r/RedReader/comments/1buzdp/my_current_todo_list_20130407_please_check_this/). Pratically, almost all of the suggestions are accepted, except in particular cases when the new features aren't pratical for the common use or in manners of particular preferences.

#### Design and implementation

The project is developed with public code, allowing users to collaborate in the development of the application, communicating with the developer through pull requests or comments. The developer decides if the code done by volunteers should be merged. Furthermore, we can see where the changes were made, when and by whom, which facilitates the collaboration on the project.
The application has a clean interface, without ads, and all the data is presented in a organized way. The main page follows *Reddit*'s structure, ordering each post and its comments by the number of upvotes. The application design makes the use of the application intuitive for the users.


#### Validation
####*"The code gets merged in immediately  (continuous integration)"* 

Back when the project was announced, every bug fix and every feature added needed a new version of the app. This created a situation where there were a huge number of versions released in  a short period of time (as you can see in [table1](#release). Nowadays, things are different, every bug fix and every new feature (almost every commit) gives origin to a new [Alpha](https://redreader.org/alpha/), an *instable* version that can be downloaded so users can try the new features and give feedback.    


#### Evolution

Because of its transparent development, which allows users to see how development proceeds, any user can suggest improvements, report bugs, request features or even develop themselves. *RedReader* can very quickly respond to changes in user’s needs. The fact that anyone can access the source code and the branches for older releases also allows users to adopt smaller changes and fixes.


---

## Process Analysis

The agile software development manifesto is based on 12 main principles which we will now compare to what we have observed from *RedReader*’s development process:

1. **Customer satisfaction by early and continuous delivery of useful software**
 
 Once in a while, the latest release of the application has bugs, so the release of the next version has to be anticipated.

2. **Welcome changing requirements, even late in development**
 
 The users can be involved in all phases of the project.

3. **Working software is delivered frequently (weeks rather than months)**
 
 Referring to the second table, the new versions don't come out every day to release a new feature or to fix some bugs and that's due to the Alpha versions. After a new version has been released and to avoid having to release a new one shortly after, any new implemented functionalities can be tested in the Alpha version by users and contributors alike.

4. **Close, daily cooperation between business people and developers**
 
 The project provides a forum to allow the communication between between business people and developers. 
 https://www.reddit.com/r/RedReader/ . 

5. **Projects are built around motivated individuals, who should be trusted**
 
 The application is a open source project, so all users can contribute to the improvement of the project. Sometimes are invited some developers to help.

6. **Face-to-face conversation is the best form of communication (co-location)**
 
 In the case of Red Reader, as the team is too small there is no need for the communication to be necessarily face to face.

7. **Working software is the principal measure of progress**
 
 Since the work being done here is on a volunteer basis, working software is the only measure of success.

8. **Sustainable development, able to maintain a constant pace**
 
 We have some doubts as to the main developers’s ability to maintain a constant pace due to the dependence on voluntary work or his own free time, despite he seeming very motivated. There is an effort towards a constant rhythm as evidenced by the evolution of the releases and the "alpha tecnic".
 
9. **Continuous attention to technical excellence and good design**
 
 Some of the new alpha versions exist in order to keep code quality.

10. **Simplicity—the art of maximizing the amount of work not done—is essential**
 
 Since the "customer" is the one who suggests new features and most of the time there's only one developer, only what's needed is developed. As said by the developer, "The most popular/useful ones go into the release".

11. **Self-organizing teams**
 
 There's only one contributor most of the time and when there's a new one, he is doing his "work" on his own organization and preference, generally working on features and changes that he himself has proposed.

12. **Regular adaptation to changing circumstance**

 Referred in 1.
 
---

## Conclusion and Alternatives

The way RedReader is being developed takes a lot of cues from the agile development principles. There is constant back and forth between developer and users, there is a quick response to change and development is geared towards prototyping (alpha versions), developers (main developer and others contributors) are self-organized and often self-sufficient prior to integration of their work.

We therefore conclude that the developer could adopt a form of agile development with a prototyping approach to the development of new features and bug fixes.

One suggestion we have is to create a release cycle. A new version should be released every month or every two months and it would usually be the latest and most stable alpha version, big enough to avoid a huge number of new versions that look alike the old ones. This method allied with the agile development principles should give a better user experience and make easier to contribute to the project 
