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

In this report we will analyze RedReader's code regarding software testing. Firstly, we will analyze various degrees of testability: controllability of tested components, observability of test results, isolateability of components, separation of concerns, understandability of components and heterogeneity of used resources. 
Then we will present the project's test statistics regarding the number of tests, coverage and other aspects. 
Finally, we will report the process of correcting a bug in the project.

---

### <a name="intro"></a> Introduction

Verification and Validation, these two terms are common in software enginnering, but what is actually the difference and why are they so important?

#### Difference between Verification and Validation

Validation is concerned with checking that the system will meet the customer's needs.
Verification is concerned with whether the system is well-engineered, error-free, etc. This will determine whether
the software is of high quality or not, but it will not ensure that is the right system.

A product can pass the verification, as it is done on paper and no running or functional application is required. However, when the same points which were verified on paper are actually developed then the running application or product can fail when validation is performed. This may happen when a product or application is built as per the specification but these specifications are not up to the mark, hence they fail to address the user requirements.

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/VV.PNG" alt="Validation and Verification"/>
</p>

---

### <a name="test"></a> Software Testability



#### <a name="cont"></a> Controllability

Defines the control degree of components to test. Starting with unit tests which are created by the developer, RedReader uses the JUnit framework. This framework offers the following:
* Find Bugs - Checks if the code has some bugs;
* Open Tasks - Searchs "TODO" comments to find if there's something missing that needs to be done;
* Code Coverage - Quantity of rows coverage by tests.

However, there's almost no tests running in this project. RedReader is using JUnit but there's only a few tests that don't cover 
almost anything and were made only for particular scenarios (the test were made to test the markdown package), almost every new feature doesn't come up with unit tests. 
Markdown package is the only exception about what was said. There's a particular test package for this package with serveral methods to (try to) find bugs.

RedReader also uses Travis CI, a github tool that is used to check if every pull request is correct and notify the main developer. Unfortunately, since there's almost no tests, this tool is potentially not being maximized, almost every pull request (even with bugs) will be accepted.
In our opinion, there is so much more that has to be improved about unit tests. 

#### <a name="obs"></a> Observability

RedReader has a poor observability. Starting with unit testing, that almost doesn't exist and even if there were many tests we would still have the same opinion. The first step is to increase the amount of unit tests, after that there are tools that increase observability, such as [jenkins](https://jenkins.io/index.html). Jenkins offers a webpage where everyone can watch the project statistics, such as build history and the results, quantity and coverage of the unit tests. It also offers some interesting information about: Checkstyle, FindBugs, Open Tasks and Code Coverage.
Therefore, we conclude that, again, there's so much to be improved.

#### <a name="isol"></a> Isolateability
RedReader is programmed in Java, an object oriented language, and sometimes, to improve the separation of concerns, we lost isolability. Therefore, when testing a function of a module A that uses another function of module B, the success of the tests performed on the function of A depends not only on the function code of that function but also on the function of module B, that is, tests can fail even if the function code of A is completely correct, so it's always difficult to look at the code and say "the isolateability is correct/incorrect". However, we think RedReader has a good isolateability, in our opinion, it will be easy to test every artifact without deeply depend in the result of another one. Our suggestion: there are libraries such as [Easy Mock](http://easymock.org/) that could be used to test the isolateability of RedReader. 

#### <a name="sep"></a> Separation of concerns

During the process of software development it is important to ensure that each functionality stays confined in the respective component, preventing the code from being confused. In projects of big dimensions, it is required a special attention to these aspects in order to avoid the occurrence of badly structure code, which increases the cost of the project's maintenance. So let's do some "digging" in RedReader to find out if each feature is confined to its component:

* RedReader is an Android application and Android applications have four main components (Activities, Services, Content providers, Broadcast receivers) therefore they should be confined to different RedReader components. There is no component in RedReader that has more than one Android component implemented.
* "RedReader downloads posts from Reddit and shows them to the user and he can also choose to save the image", this is a scenario that expresses how well the separation of concerns is implemented: "RedReader downloads posts from Reddit (...)" To do this, RedReader has a component that only serves to download information between Reddit and RedReader and another component that makes that connection; "(...) shows them [posts] to the user (...)", RedReader has several components dedicated only to interact with users; "(...) the user can also choose to save the image" This last action is structured in three differentiated components, one is responsible for user interaction with the application, the second component has cached the image, and a third component that effectively saves an image.

Therefore, we can only conclude that the separation of concerns in RedReader is correct.

#### <a name="und"></a> Understandability

RedReader's understandability is probably its weakest point. RedReader does not have any type of documentation, the only information available to explain RedReader is the one that is presented on the PlayStore.

The code also does not have any type of comment, only a header to explain the license of the project.

This complicates the task of those who want to contribute to the project, because it is difficult to create a new functionality when you do not know where every dependecy is implemented, for inexperienced programmers in Android it is practically impossible to contribute.

To demonstrate the problem of bad code comprehensibility, when we had to correct the bug mentioned below, we had to reverse engineer the code, in other words, we already knew what to do and how to correct the code, we just did not know where the code was. So, based on what was shown on the screen at the time of the bug, it was reverse engineered until it reached the basis of the problem. Good documentation would avoid this whole work and help maintain code consistency.


#### <a name="het"></a> Heterogeneity
RedReader is a project with a huge heterogeneity since it uses several external technologies to execute. Some of those technologies are:

* **[OkHttp](https://github.com/square/okhttp):** "An HTTP & HTTP/2 client for Android and Java applications."
* **[NetCipher](https://github.com/square/okhttp)** "a library for Android that provides multiple means to improve network security in mobile applications."
* **[jackson-core](https://github.com/square/okhttp)** "core low-level incremental ("streaming") parser and generator abstractions used by Jackson Data Processor."
* **[joda-time](https://github.com/square/okhttp)** "provides a quality replacement for the Java date and time classes."

---

### <a name="tests"></a> Test Statistics

#### Dynamic Testing

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

#### Static Testing

Seeing as there was not much to analyze in the dynamic tests, we decided to do a static analysis using [Codacy](https://www.codacy.com/).

The analysis is based on each of the following categories:

* Code Style - Code formatting and syntax problems. Ex: variable name style, enforce the use of brackets and quotation marks
* Error Prone - Code that may hide bugs and language keywords that should be used with caution. Ex: == in Javascript or Option.get in Scala
* Code Complexity - Highly complex methods and classes that should be refactored
* Performance - Code that could have performance problems
* Compatibility - Used mainly for frontend code, detects compatibility problems across different browser versions
* Unused Code - Unused variables and methods, code that can't be reached
* Security - Security problems.
* Documentation - Detects methods and classes that do not have the correct comment annotations

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/codacyResults.png" alt="Codacy Results"/>
</p>

There are no issues with the compatibility and performance. The use of the NetCipher library means there are also no problems regarding the project's security. 

As expected, there are a few issues regarding code style and unused code, but nothing major that would hinder the project. However, the results regarding error proneness were not as satisfactory and it is definitely something that could be worked on to further improve the code's quality.

Unfortunately we could not get any results regarding code complexity and documentation.

All in all, the results were mostly positive, granting a project quality rank of B (on their scale ranging from F to A).

---

### <a name="bug"></a> Bug Report

We solved bug [#411](https://github.com/QuantumBadger/RedReader/issues/411) presented in Github's issues list.

#### Information:
RedReader lets you save images presented on the screen and it saves the images with a filename equal to the image's url. The problem is that Reddit created a new feature to upload images and those images' url don't have an extension, therefore, when RedReader saves it, the image can't be opened because there's no extension.
 
#### Resolution:

We tried several aproaches to resolve this bug. We already knew that this problem only happens with images, therefore, we just insert the extension in the end of the filename. This looked like a naive resolution, but we tried to use libraries that could "guess" the mimeType and we didn't have any success because those libraries don't work well with InputStream.

#### Pull Request

We created a new fork of RedReader and made a [pull request](https://github.com/QuantumBadger/RedReader/pull/415) so that our bug fix can be evaluated by Travis CI and accepted by the main developer of RedReader

#### Unit Test

We did not include any test (on the pull request) because there's almost no tests in RedReader. However, we did create a unit test to confirm our approach to fix the bug:

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/bug%20fix.PNG" alt="Unit Test"/>
</p>
