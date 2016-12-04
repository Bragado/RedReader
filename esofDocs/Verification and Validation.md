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

---

### <a name="intro"></a> Introduction

In this report we will analyze redReader's code with regard to software tests. First will be analyzed degrees of testability: controllability of tested components, observability of test results, isolateability of components, separation of concerns, understandability of components and heterogeneity of used resources. 
Then will be presented project's test statistics with regard of number of tests, coverage and other aspects. 
Finally, will be reported the process of correcting a bug in the project.

---

### <a name="test"></a> Software Testability

#### <a name="cont"></a> Controllability

Defines the control degree of components to test. Starting with unit tests who are created by developer, redReader uses JUnit framework. This framework offers:
* FindBugs - Checks if code have some bugs;
* Open Tasks - searchs comments #TODO" to find if is missing something to do;
* Code Coverage - quantity of rows coverage by tests.
However, there's almost no test running in this project. RedReader is using JUnit but there's only a few tests that don't cover almost anything and were made only for particular scenarios, almost every new feature don't come up with unit tests. In our opinion there is so much more that has to be improved about unit tests.
RedReader also uses Travis CI. "When Travis CI has been activated for a given repository, GitHub will notify it whenever new commits are pushed to that repository or a pull request is submitted. It can also be configured to only run for specific branches, or branches whose names match a specific pattern. Travis CI will then check out the relevant branch and run the commands specified in .travis.yml, which usually build the software and run any automated tests." But again, this tool potential is not being maximized in this project.

#### <a name="obs"></a> Observability

RedReader has a poor observability. Starting with unit test, that almost doesn't exist and even if there was many tests we would still have the same opnion. The first step is to increase the amount of unit tests then, there are tools that increase observability, such as [jenkins](https://jenkins.io/index.html). Jenkins offers a webpage where everyone can watch the project statics, such as build historic and the results, quantity and coverage of the unit tests. It also offers some interesting information about: Checkstyle, FindBugs, Open Tasks and Code Coverage.
Therefore, we conclude that again, there's so much to be improved.

#### <a name="isol"></a> Isolateability
This is always a complex topic and most of the time hard to classify. When testing a function of a module A that uses another function of module B, the success of the tests performed on the function of A depends not only on the function code of that function but also on the function of module B, that is, tests can fail Even if the function code of A is completely correct so, it's always difficult to look at the code and say "the isolateability is correct/incorrect". However, there are libraries such as [Easy Mock](http://easymock.org/) that could be use to test the isolateability of RedReader. 

#### <a name="sep"></a> Separation of concerns

During the process of software development it is important to ensure that each functionality stays confined in the respective component, preventing the code from being confused. In projects of big dimensions is required a special attention at this aspects to avoid the occurrence of badly structure code, what increases the cost of project's maintenance. So let's do some "digging" in RedReader to find out if each feature is confined to its component:

* RedReader is an Android application and Android applications have four main components (Activities, Services, Content providers, Broadcast receivers) therefore they should be confined to different RedReader components. There is no component in RedReader that has more than one Android component implemented.
* "RedReader downloads posts from Reddit and shows them to the user and he can also choose to save the image", this is a scenario that expresses how well the separation of concerns is implemented: "RedReader downloads posts from Reddit... " To do this, RedReader has a component that only serves to download information between Reddit and RedReader and another component that makes that connection; "... shows them [posts] to the user ...", RedReader has several components to, only, interact with users; "... the user can also choose to save the image ..." This last action is structured in three differentiated components, one is responsible for user interaction with the application, the second component has cached the image, and a third component that effectively saves an image.

Therefore, we can only conclude that the separation of concerns in RedReader is correct.

#### <a name="und"></a> Understandability

#### <a name="het"></a> Heterogeneity
RedReader is a project with a huge heterogeneity since it uses several external technologies to execute. Some of those technologies are:

* **[OkHttp](https://github.com/square/okhttp):** "An HTTP & HTTP/2 client for Android and Java applications."
* **[NetCipher](https://github.com/square/okhttp)** "a library for Android that provides multiple means to improve network security in mobile applications."
* **[jackson-core](https://github.com/square/okhttp)** "core low-level incremental ("streaming") parser and generator abstractions used by Jackson Data Processor."
* **[joda-time](https://github.com/square/okhttp)** "provides a quality replacement for the Java date and time classes."

---

### <a name="tests"></a> Test Statistics

---

### <a name="bug"></a> Bug Report

