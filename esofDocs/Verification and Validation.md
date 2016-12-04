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
FindBugs - Checks if code have some bugs;
Open Tasks - searchs comments #TODO" to find if is missing something to do;
Code Coverage - quantity of rows coverage by tests.

#### <a name="obs"></a> Observability

RedReader uses the framework JUnit. With this framework can be verified if each method of a class works as expected. JUnit allows the quick creation of tests code increasing the quality of developing of application.
The observability of test results is easy through JUnit. 

#### <a name="isol"></a> Isolateability

#### <a name="sep"></a> Separation of concerns

During the process of software development it is important to ensure that each functionality stays confined in the respective component, preventing the code from being confused. In projects of big dimensions is required a special attention at this aspects to avoid the occurrence of badly structure code, what increases the cost of project's maintenance. So let's do some "digging" in RedReader to find out if each feature is confined to its component:

* RedReader is an Android application and Android applications have four main components (Activities, Services, Content providers, Broadcast receivers) therefore they should be confined to different RedReader components. There is no component in RedReader that has more than one Android component implemented.
* "RedReader downloads posts from Reddit and shows them to the user and he can also choose to save the image", this is a scenario that expresses how well the separation of concerns is implemented: "RedReader downloads posts from Reddit. .. " To do this, RedReader has a component that only serves to download information between Reddit and RedReader and another component that makes that connection; "... shows them [posts] to the user ...", RedReader has several components to, only, interact with users; "... the user can also choose to save the image ..." This last action is structured in three differentiated components, one is responsible for user interaction with the application, the second component has cached the image, and a third component that effectively saves an image.

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

