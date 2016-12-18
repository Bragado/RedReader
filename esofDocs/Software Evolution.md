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

In this report we will analyze RedReader's code regarding software evolution. Firstly, we will discuss software maintainability using the SIG metrics. Then we will report evolution process implementing a feature that we have chosen, describing how the feature was identified,
why did we chosen that feature and how did we located the parts in the source code that needed to be modified.

---

### <a name="intro"></a> Introduction


---

### <a name="maint"></a> Software maintainability

The following results were obtained using the service https://bettercodehub.com:

<p align="center">
  <img src="https://github.com/Bragado/RedReader/blob/master/esofDocs/img/maintenance.png" alt="Maintenance"/>
</p>

#### 1.*"Write Short Units of Code"*

RedReader does not limit the length of code units (smallest groups of code that can be maintained and executed independently) to 15 lines of code. It has long units which becomes hard to test, reuse and understand.

#### 2.*"Write Simple Units of Code"*

One of the disputed characteristic of maintainability is complexity of code.
The RedReader's code has a higher number of branch points. A branch point is a statement where execution can take more than one direction depending on a condition. This makes the code complex that modifying it becomes extremely risky and a very time-consuming task.

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

Redreader contains only 1 component (minimising the amount of interface code). At this point, it is essential avoid interface modules that put through calls to other components and limit the size of modules that are the component’s interface.

#### 7.*"Keep Architecture Components Balanced"*
#### 8.*"Keep Your Codebase Small"*

Keeping codebase small improves maintainability, as it's less work to make structural changes in a smaller codebase. RedReader keeps volume below 20 Man-years (about 39 Man-Months).
In a small system it is easier to search through code, analyze and understand it. This ease of maintenance leads to fewer mistakes and lower costs.
Technical adjustments such as refactoring and reuse of functionality are easier with a small system and will be beneficial for all further coding.

#### 9.*"Automate Tests"*

Automated testing makes development efficient and can be executed with much less effort than manual tests. Automating tests for codebase makes development more predictable and less risky.
RedReader features about 28,000 lines of code, with only 245 (<1.0%) test code lines, and assert density below the recommended 5%.

#### 10.*"Write Clean Code"*

RedReader presents a very clean code, not making use of useless comments or annotated code blocks and dead code. This is an asset, as a cleaner code is more maintainable code.

---

### <a name="evol"></a> Evolution process

#### <a name="ident"></a> Feature identification

#### <a name="change"></a> Changes in the source code

---

### <a name="pull"></a> Pull request
