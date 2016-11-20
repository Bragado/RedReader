## Software Design for RedReader

## Authors

* Diana Isabel Garcia Pinto
* João Henrique Poceiro Vieira de Araújo
* Luís Filipe Rodrigues Coelho
* Marisa Daniela Quintal Oliveira

---

### Table of Contents
1. [Introduction](#intro)
2. [Views](#views)    
  1. [Logical view](#logical)
  2. [Development view](#development)
  3. [Process view](#process)
  4. [Deployment view](#deployment)


---

### Abstract

At this stage we will describe the software structure of RedReader, based on the source code and the project documentation, made available.
Poorly designed architectures can lead to instabilities, inability to support requirements - present or future - and difficulty in applying or managing the production environment. This is where software architecture comes in - the fundamental organization of a system, formed by its components, the relationships between them and the principles that shape its design and evolution. Our approach to RedReader architecture will be based on model 4 + 1 software architecture views. The 4 views represent the logical view, implementation view, process view and distribution view, with the additional view (+1) being the use-cases view, the diagram of which has already been presented in the last report.

---

### <a name="intro"></a> Introduction

The 4+1 View Model describes software architecture using five concurrent views. Often, software engineers wonder: *“what do we want to do”* or *“how are we going to it”* so, they need a model that defines how they can divide the system in modules and how can they be connected with each other. This concerns divide the system in components that *“can be developed in parallel and subsequently integrated, and identify opportunities for reuse.”* In order to do that we need a specific set of concerns with the 4+1 View Model: "The logical view describes the design's object model, the process view describes the design's concurrency and synchronization aspects; the physical/deployment view describes the mapping of the software onto the hardware and shows the system's distributed aspects, and the development view describes the software's static organization in the development environment. Software designers can organize the description of their architectural decisions around these four views and then illustrate them with a few selected use cases, or scenarios, which constitute a fifth view. The architecture is partially evolved from these scenarios. The 4+1 View Model allows various stakeholders to find what they need in the software architecture. System engineers can approach it first from the physical view, then the process view; end users, customers, and data specialists can approach it from the logical view; and project managers and software-configuration staff members can approach it from the development view."
 
This report  will be about RedReader 4+1 View Model as said before. We alert that RedReader has no documentation available neither any type of document discribing each package/classe implemented, also, there’s no comments in the code therefore, this report can be wrong in some sections, but we did our best to avoid it.

For the logic view we will have another file, to analyse a litle better this section. 


### <a name="views"></a> Views

#### <a name="logical"></a> Logical View

#### <a name="development"></a> Development View

#### <a name="process"></a> Process View

#### <a name="deployment"></a> Deployment View
