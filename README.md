# AnyVer
AnyVer tries to introduce a better versioning system for the products with temporal progressive natures.
# Preface
As this specification is the rightful place of using the terminology of the Lean methodology, its a good idea to unofficially call it `LeanVer`, but since "AnyVer" assumes the top place in lexicographical sortings and is a cool name as well, it is wiser to keep with it as the official naming. Anyway we all know that Lean is Anywhere.

Additionally:
- It is written **AnyVer** Because it can encapsulate any **glance necessary information** about iterations of a project in a compatible way with the building and integration tools.

- It is read **AnyWhere** Because its applicable any where, from versioning the code components of software projects to the mechanical components in a space rocket project, any thing intended to be assembled or integrated somewhere.
# Introduction
Between two products in a supply chain relationship with one another,
The one that offers some features to the others is called **upstream product**, i.e. the one that other parties rely on its features.
The **downstream product** is the opposite side, i.e. the product that makes use of the features offered by the upstream product. 
As an example, a crude copper refinery produces pure copper which is upstream of the wire production plants.
Or C++ is upstream of Python which it self is upstream of Scipy which is upstream of scikit-learn and so on.

**`Bumping the Version number`**: Lets assume a version number of 0.1.0 for a projects product. Once it has evolved enough, the maintainer might decide to release the next version with the name 0.1.1. Then it is said that its patch number (or micro number in the Python world) has bumped. If it goes to the version 0.2.0 then its minor number has bumped. And having it incremented to the version number 1.0, we say its versions major number has bumped. Using patterns like **Major**.**Minor**.**Patch** is the standard way of versioning in the software industry.

**`Backward Compatibility`**: In the world of computer programming, backward compatibility of a released software iteration, is interpreted as being able to upgrade this software in the projects which use it, keeping them pass all their tests like how they did with the old release, without any changes to the projects code itself.
But such a situation is very rare. Even a small change in a single line of a piece of code, may introduce lots of errors and failures in the downstream tests.
Relying on this definition, for iteration of the "major" part can lead to rapidly growing meaningless version numbers.    
Thats why its necessary to narrow down the definition of compatibility into smaller classes that bind the number bumping triggers to some more meaningful events.

**`Kaizen, Kaikaku, Kakushin:`**:
Due to the verstile and comprehensive concepts found in the Lean methodology, AnyVer adopts and brings some of this terminology into the subject of software versioning.
During the course of life of a software project, there may occur two types of changes, some of which bring backward incompatiblity with them:
1. **Evolutionary Changes**:
Being called Kaizen in the Lean methodology, these small enhancements may have no external cause, and occur solely due to the continuous fine processing of the product by the staff. Or it might be a response by a downstream product team to such evolutionary changes of the upstream products. But the second practice is avoidable on its own if these small changes bring costly incompatiblity. Because no matter how tiny it is, introducing incompatibitily in the favor of small enhancements absorbed from the upstream products, might be expensive and cost ineffective for a product and its downstream users.
There are atleast 3 types of Kaizen:
   - Bugfixes
   - Performance upgrades
   - Functional upgrades

   Incompatibility introduced by these kind of changes, is usually promptly addressable by adding or removing some lines of code here and there. Or even if it requires a lot of code refactor, it still doesn't affect the architecture of the software. And the codes schematic diagrams(like UML, StateFlow...) nearly remain the same before and after resolution of the change waves.
Finally making such decisions is all about competition, teams may rather to mirror a bunch of small changes of the upstream products as its side-effect enhancements during a bigger Revolutionary change.
2. **Revolutionary Changes**:
Not every radical change is a revolutionary one, but every revolutionary change brings radical refactors with it.
At the Upstream it can be a revolution in Quantum Mechanics leading to revolutions in the propellants downstream in the space rocket industry. A revolution in CPU or GPU architectures, leading to drastic changes in the instruction sets consequently some revolutionary features go to bubble up in the programming languages which will render some of the old libraries obsolete ending up as major sudden changes in the software codes. Or even a revolution in Python Steering Council may cause an upheaval in the Pythons PEPs and major revolutionary changes in projects relying on it.
These changes might be welcomed by the affected project maintainers in order to keep up with the technology advances, or it may be a forceful decision because the upstream providers may opt to desert support of the old stuff, or even its a response to the recent market expectations because of the emergence of new competitors with great ideas.
**`Glance necessary information`**:     
One may look on the version of a products iteration in order to know:
1. When was its first release?
2. When was its latest release"
3. How old is it?
4. How mature is it, or how many revolutions has it experienced?
5. In the latest year of development:
   - How many functional upgrades has it had?
   - How many performance upgrades has it had?
   - How many Bugfix patches has it had?
   - etc.
6. Is it in pre-release or post-release phase?
7. And optionally, what is 
# Details
Full details
# Examples
Some examples...
If you have 
# Used By
...
# Attributes
Some of the content in this specification is borroed from other publicly available specifications like [SemVer](https://semver.org/) and [CalVer](https://calver.org/)
# Contributing
See the [contribution guide](https://github.com/SKhajeh/anyver/blob/main/CONTRIBUTING.MD)
# License
For now its licensed under terms of `CC BY-ND 4.0`. A relicense with more permissible terms is up to come once it matured enough.
