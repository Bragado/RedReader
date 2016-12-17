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

RedReader does not limit the length of code units to 15 lines of code. It has long units which becomes hard to test, reuse and understand.

#### 2.*"Write Simple Units of Code"*

The code has a higher number of branch points. A branch point is a statement where execution can take more than one direction depending on a condition. This makes the code complex that modifying it becomes extremely risky and a very time-consuming task.

#### 3.*"Write Code Once"*

The code has a lot of duplicated code. This is not good, because when code is copied, bugs need to be fixed at multiple places, which is inefficient and error-prone.

#### 4.*"Keep Unit Interfaces Small"*
#### 5.*"Separate Concerns in Modules"*
#### 6.*"Couple Architecture Components Loosely"*
#### 7.*"Keep Architecture Components Balanced"*
#### 8.*"Keep Your Codebase Small"*
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
