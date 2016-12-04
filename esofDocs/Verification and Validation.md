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

During the process of software development it is important to ensure that each functionality stays confined in the respective component, preventing the code from being confused. In projects of big dimensions is required a special attention at this aspects to avoid the occurrence of badly structure code, what increases the cost of project's maintenance. In this way, redReader separates each functionality to the respective module, having a folder only for the tests.

#### <a name="und"></a> Understandability

#### <a name="het"></a> Heterogeneity

---

### <a name="tests"></a> Test Statistics

---

### <a name="bug"></a> Bug Report

