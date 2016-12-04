## Verification and Validation

## Authors

* Diana Isabel Garcia Pinto
* João Henrique Poceiro Vieira de Araújo
* Luís Filipe Rodrigues Coelho
* Marisa Daniela Quintal Oliveira

---
## Table of Contents
1. [Introduction](#intro)
2. [Software Testability](#test)
  1. [Controllability](#cont)
  2. [Observability](#obs)
  3. [Isolateability](#isol)
  4. [Separation of concerns](#sep)
  5. [Understandability](#und)
  6. [Heterogeneity](#het)
3. [Test Statistics](#tests)
4. [Bug Report](#bug)


### Abstract

In this report we will analyze redReader's code with regard to software tests. First will be analyzed degrees of testability: controllability of tested components, observability of test results, isolateability of components, separation of concerns, understandability of components and heterogeneity of used resources. 
Then will be presented project's test statistics with regard of number of tests, coverage and other aspects. 
Finally, will be reported the process of correcting a bug in the project.

---

### <a name="intro"></a> Introduction



---

### <a name="test"></a> Software Testability



#### <a name="cont"></a> Controllability

Defines the control degree of components to test. Starting with unit tests who are created by developer, redReader uses JUnit framework. This framework offers:
* FindBugs - Checks if code have some bugs;
* Open Tasks - searchs comments #TODO" to find if is missing something to do;
* Code Coverage - quantity of rows coverage by tests.

However, there's almost no test running in this project. RedReader is using JUnit but there's only a few tests that don't cover 
almost anything and were made only for particular scenarios (the test were made to test markdown package), almost every new feature don't come up with unit tests. 
Markdown package is the only exception about what was said. There's a particular test package for this package with serveral methods to (try to) find bugs.

RedReader also uses Travis CI, a github tool that is used to check if every pull request is correct and notify the main developer. However, since there's almost no tests,
this tool potential is not being maximized, almost every pull request (even with bugs) will be accepted.
In our opinion there is so much more that has to be improved about unit tests. 

#### <a name="obs"></a> Observability

RedReader has a poor observability. Starting with unit test, that almost doesn't exist and even if there was many tests we would still have the same opnion. The first step is to increase the amount of unit tests then, there are tools that increase observability, such as [jenkins](https://jenkins.io/index.html). Jenkins offers a webpage where everyone can watch the project statics, such as build historic and the results, quantity and coverage of the unit tests. It also offers some interesting information about: Checkstyle, FindBugs, Open Tasks and Code Coverage.
Therefore, we conclude that again, there's so much to be improved.

#### <a name="isol"></a> Isolateability
RedReader is programmed in Java, an object oriented language, and sometimes, to improve the separation of concerns, we lost isolability. Therefore, when testing a function of a module A that uses another function of module B, the success of the tests performed on the function of A depends not only on the function code of that function but also on the function of module B, that is, tests can fail Even if the function code of A is completely correct so, it's always difficult to look at the code and say "the isolateability is correct/incorrect". However, we thing RedReader has a good isolateability, in our opinion, it will be easy to test every artifact without deeply depend in the result of another one. Our suggestion: there are libraries such as [Easy Mock](http://easymock.org/) that could be use to test the isolateability of RedReader. 

#### <a name="sep"></a> Separation of concerns

During the process of software development it is important to ensure that each functionality stays confined in the respective component, preventing the code from being confused. In projects of big dimensions is required a special attention at this aspects to avoid the occurrence of badly structure code, what increases the cost of project's maintenance. So let's do some "digging" in RedReader to find out if each feature is confined to its component:

* RedReader is an Android application and Android applications have four main components (Activities, Services, Content providers, Broadcast receivers) therefore they should be confined to different RedReader components. There is no component in RedReader that has more than one Android component implemented.
* "RedReader downloads posts from Reddit and shows them to the user and he can also choose to save the image", this is a scenario that expresses how well the separation of concerns is implemented: "RedReader downloads posts from Reddit... " To do this, RedReader has a component that only serves to download information between Reddit and RedReader and another component that makes that connection; "... shows them [posts] to the user ...", RedReader has several components to, only, interact with users; "... the user can also choose to save the image ..." This last action is structured in three differentiated components, one is responsible for user interaction with the application, the second component has cached the image, and a third component that effectively saves an image.

Therefore, we can only conclude that the separation of concerns in RedReader is correct.

#### <a name="und"></a> Understandability

RedReader's understandability is probably its weakest point. RedReader does not have any type of documentation, the only information available to explain RedReader is the one that is present on PlayStore.

The code also does not have any type of comment, only one has a header to explain the license of the project.

This complicates the task of those who want to contribute to the project, because it is difficult to create a new functionality when you do not know where every dependecy is implemented, for inexperienced programmers in Android it is practically impossible to contribute.

To demonstrate the problem of bad code comprehensibility, when we had to correct the bug mentioned below, we had to reverse engineer the code, that is, we already knew what to do and how to correct the code, we just did not know where the code was. So, based on what was shown on the screen at the time of the bug, it was reverse engineered until it reached the basis of the problem. Good documentation would avoid this whole work and help maintain code consistency.


#### <a name="het"></a> Heterogeneity
RedReader is a project with a huge heterogeneity since it uses several external technologies to execute. Some of those technologies are:

* **[OkHttp](https://github.com/square/okhttp):** "An HTTP & HTTP/2 client for Android and Java applications."
* **[NetCipher](https://github.com/square/okhttp)** "a library for Android that provides multiple means to improve network security in mobile applications."
* **[jackson-core](https://github.com/square/okhttp)** "core low-level incremental ("streaming") parser and generator abstractions used by Jackson Data Processor."
* **[joda-time](https://github.com/square/okhttp)** "provides a quality replacement for the Java date and time classes."

---

### <a name="tests"></a> Test Statistics

The developer seems to rely mostly on manual testing, as shown by the very limited amount of automated tests. In that regard, it's probably one of the weakest areas of the project.

The following results were obtained using Intellij IDEA code coverage tool:

* Number of unit tests: 22

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/testCoverageOverall.png" alt="Overall Coverage"/>
</p>

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/testCoveragePackage.png" alt="Package Coverage"/>
</p>

As we can see, almost nothing is covered, pretty much all tests are unit tests revolving around the Markdown Tokenizer. Since this is a rather small-scale project, the developer clearly didn't bother much with automated testing, resorting almost always to manual testing and bugs found by users.

---

### <a name="bug"></a> Bug Report

We solved bug [#411](https://github.com/QuantumBadger/RedReader/issues/411) presented in github issues list

#### Information:
RedReader let's you save images presented on the screen and RedReader saves the images with a filename equals to the image url.  The problem is that Reddit created a new feature to upload images and those images url don't have extenetion therefore, when RedReader saves it, the image can't be open because there's no extension.
 
#### Resolution:

We tried several aproaches to resolve this bug. We already knew that this problem only happens with images therefore, we just insert the extension in the end of the filename. This looked like a naive resolution, but we tried to use libraries that could "guess" the mimeType and we didn't have any success because those libraries don't work well with InputStream.

#### Pull Request

We created a new fork of ReadReader and made a [pull request](https://github.com/QuantumBadger/RedReader/pull/415) so that, our bug fix, can be evaluated by Travis CI and accepted by the main developer of RedReader

#### Unit Test

We did not include any test (on the pull request) because there's almost no tests in RedReader however, we created a unit test to confirm our approach to fix the bug:

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/bug%20fix.PNG" alt="Unit Test"/>
</p>
