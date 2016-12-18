## Software Evolution

## Authors

* Diana Isabel Garcia Pinto
* João Henrique Poceiro Vieira de Araújo
* Luís Filipe Rodrigues Coelho
* Marisa Daniela Quintal Oliveira

---
## Table of Contents
1. [Introduction](#intro)
2. [Software maintainability](#maint)
3. [Evolution process](#evol)
  1. [Feature identification](#ident)
  2. [Changes in the source code](#change)
4. [Pull request](#pull)

### Abstract

In this report we will analyze RedReader's code regarding Software Evolution. Firstly, we will discuss software maintainability using the SIG metrics. Then we will report the evolution process of implementing a feature that we have chosen, describing how the feature was identified, why we chose that feature and how we located the parts in the source code that needed to be modified.

---

### <a name="intro"></a> Introduction

Software change is inevitable. Evolution starts from the process of gathering of requirements. Developers create a prototype of the intended software and then the they show it to the users to get feedback from the users at the early stage of software product development. The users suggest changes, on which several updates and maintenance keep on changing too. This process changes the original software, until the desired software is accomplished. Re-creating software from scratch and to go one-on-one with requirement is not feasible. The only feasible and economical solution is to update the existing software so that it matches the latest requirements.
Maintainability is defined as the ease with which changes can be made to a software system. Four types of software maintenance can be distinguished:

* Corrective maintenance (fix bugs who are discovered)
* Adaptive maintenance (the system has to be adapted to changes in the environment in which it operates)
* Perfective maintenance (users of the system have new or changed requirements)
* Preventive maintenance (ways are identified to increase quality or prevent future bugs from occurring) 

Maintainability is a special aspect of software quality, it acts as an enabler for other quality characteristics. When a system has high maintainability it will be easier to make improvements in the other quality aspects, such as fixing a security bug. 
Optimizing a software system requires modifications to its source code. Sometimes they are small, local modifications. Sometimes it involves more invasive restructuring. All modifications require finding a specific piece of source code and analyzing it. In a more maintainable system these modifications are easier to make, allowing to pull off quality optimizations faster and more effectively.

---

### <a name="maint"></a> Software maintainability

The following results were obtained using the service https://bettercodehub.com:

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/maintenance.png" alt="Maintenance"/>
</p>

#### 1.*"Write Short Units of Code"*

RedReader does not limit the length of code units (smallest groups of code that can be maintained and executed independently) to 15 lines of code. It has long code units which makes it hard to test, reuse and understand.

#### 2.*"Write Simple Units of Code"*

One of the disputed characteristic of maintainability is complexity of code.
The RedReader's code has a higher than ideal number of branch points. A branch point is a statement where execution can take more than one direction depending on a condition. This makes the code so complex that modifying it becomes extremely risky and a very time-consuming task.

#### 3.*"Write Code Once"*

All code may contain bugs. If the duplicate code contains a bug, the same error will appear several times.
The RedReader’s code has a lot of duplicated code. This is not good, because when code is copied, bugs need to be fixed at multiple places, which is inefficient and error-prone.

#### 4.*"Keep Unit Interfaces Small"*

Methods with small interfaces keep their context simple and thus easier to understand.
At least 30 units of RedReader's code have more than 4 parameters for unit at RedReader's code. This makes the units hard to understand and reuse.

#### 5.*"Separate Concerns in Modules"*

Keeping classes small provides a direct path towards loose coupling between classes. This means that class level design will be much more flexible to facilitate future changes, in other words, changes can be made while limiting unexpected effects of those changes.
RedReader's code has large modules. This can't get loose couplings between them. Therefore, changes in code-base are hard to oversee and execute.

#### 6.*"Couple Architecture Components Loosely"*

Redreader contains only 1 module (minimizing the amount of interface code). At this point, it is essential to avoid interface modules that put through calls to other components and limit the size of modules that are the component’s interface.

#### 7.*"Keep Architecture Components Balanced"*

The number of top-level system components should ideally be 9, generally between 6 and 12, and the components’ volume in terms of source code should be roughly equal. However, Redreader contains only 1 component, this can be a disadvantage in the case of projects involving a team with a division of responsibilities.

#### 8.*"Keep Your Codebase Small"*

Keeping codebase small improves maintainability, as it's less work to make structural changes in a smaller codebase. RedReader keeps volume below 20 Man-years (about 39 Man-Months).
In a small system it is easier to search through code, analyze and understand it. This ease of maintenance leads to fewer mistakes and lower costs.
Technical adjustments such as refactoring and reuse of functionality are easier with a small system and will be beneficial for all further coding.

#### 9.*"Automate Tests"*

Automated testing makes development efficient and can be executed with much less effort than manual tests. Automating tests for the codebase makes development more predictable and less risky.
RedReader features about 28,000 lines of code, with only 245 (<1.0%) test code lines, and assert density below the recommended 5%.

#### 10.*"Write Clean Code"*

RedReader presents a very clean code, not making use of useless comments or annotated code blocks and dead code. This is an asset, as a cleaner code is more maintainable code.

---

### <a name="evol"></a> Evolution process

#### <a name="ident"></a> Feature identification

As stated in the previous report, RedReader has a list of issues in gitbug. All bugs and suggestions for new
Features are described in this list. Initially, we attempted to implement the suggestion of direct sharing of images, however, before we finished the implementation, another developer did [pull request](https://github.com/QuantumBadger/RedReader/issues/413) of the same feature and was accepted. As such, the members of our group have chosen to implement another feature suggestion.
 
The [implemented feature](https://github.com/QuantumBadger/RedReader/pull/422), "Display size when loading images", shows the progress of the image download in
Megabytes.


#### <a name="change"></a> Changes in the source code

---

### <a name="pull"></a> Pull request
