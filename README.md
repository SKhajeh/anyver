# AnyVer
Anyhow Versioning tries to introduce a better versioning system for the products with temporal progressive natures.
# Preface
As this specification is the rightful place of using the terminology of the Lean methodology, its a good idea to unofficially call it `LeanVer`, but since "AnyVer" assumes the top place in lexicographical sortings and is a cool name as well, it is wiser to keep up with it as the official naming. Anyway we all know that Lean is Anywhere.

Additionally:
- It is written **AnyVer** Because it encapsulates any [**glance necessary information**](gni) about iterations of a project in a compatible way with the building and integration tools.

- It is read **AnyWhere** Because its applicable any where, from versioning the code components of software projects to the mechanical components in a space rocket project, any thing intended to be assembled or integrated somewhere.

<a name=gni>**`Glance necessary information`**:</a>     
One may look on the version of a products iteration in order to know:
1. When was its first release?
2. When was it last released"
3. How old is it?
4. How mature is it, or how many revolutions has it experienced?
5. How active is it, or In the latest month of development:
   - How many releases with functional modification has it had?
   - How many releases with performance upgrades has it had?
   - How many releases with bugfixes has it had?
   - etc.
6. Is it in pre-release or post-release phase?
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

**`LeanVer:`**:
Due to the verstile and comprehensive concepts made available by the Lean methodology, AnyVer adopts and brings some of this terminology into the subject of software versioning.
During the course of life of a software project, there may occur two types of changes, some of which bring backward incompatiblity with them:
1. **Evolutionary Changes**:
Being called **`Kaizen`** in the Lean methodology, these small enhancements may have no external reason, and occur solely due to the continuous fine processing of the product by the staff. Or it might be a response by a downstream product team to such evolutionary changes of the upstream products. But the second practice is avoidable on its own if these small changes bring costly incompatiblity. Because no matter how tiny it is, introducing incompatibitily in the favor of small enhancements absorbed from the upstream products, might be expensive and cost ineffective for a product and its downstream users.    
<a name= FPB>There are at least 3 types of Kaizen:</a>
   - Bugfixes: Any changes related to correcting the unintended presentation or behaviours. Like a harmless redundant warning or some misleading info in the docs.
   - Performance upgrades: Manipulations that enhances performance of the product.
   - Functional modifications: When a feature is deprecated in favor of another newly introduced one, or a new feature is added.

   Incompatibility introduced by these kinds of change, is usually promptly addressable by adding or removing some lines of code here and there. Or even if it requires a lot of code refactor, it still doesn't affect the architecture of the software. And the codes schematic diagrams(like UML, StateFlow...) don't experience a global variation when compared before and after carrying out of the commits. Thus AnyVer categorizes these class of changes(F,P,B) in the **`backward non-destructive`** group meaning if at all it is going to cause some refactoring downstream, it will be in a non-destructive way to the overall architecture of its dependant products.
Finally making such decisions is all about competition, teams may rather to mirror a bunch of small changes of the upstream products as its side-effect enhancements during a bigger Revolutionary change.
2. **Revolutionary Changes**:
Not every radical change is a revolutionary one, but every revolutionary change brings radical refactors with it.
A revolution in Quantum Mechanics Upstream can lead to revolutions in the propellants, downstream in the space rocket industry. A revolution in CPU or GPU architectures, leading to drastic changes in the instruction sets and consequently some new features go to bubble up in the programming languages which will render some of the old libraries obsolete ending up in major sudden changes of the software codes. Or even a revolution in Python Steering Council may cause an upheaval in the Pythons PEPs and major revolutionary changes in projects relying on it.
These changes might be welcomed by the affected project maintainers in order to keep up with the technology advances, or it may be a forceful decision because the upstream providers may opt to desert support of the old stuff, or even its a response to the recent market expectations because of the emergence of new competitors with great ideas.
Lean defines 2 types of revolutionary changes:
   - **Kaikaku**, meaning the radical movements which totally change the view of the current situation. In software programming, the introduction of async keyword and asynchronous functions in Python(in a competition with NodeJS's asynchronous constructs) to replace the @async decorators is an example, which gradually moved down in the supply chain afterwards when the people developing Python API's (e.g. for the online exchanges), at some point deserted the old synchronous style and adopted this new upstream pushed feature. In terms of AnyVer, if the product is changing drastically internally or publicly, and in each release it has sub-level stability then it is undergoing its Kaikaku changes.
   - **Kakushin**, meaning the extreme turns which fundamentally transform the current situation. There are lots of once busy now abandoned production lines, just because at some point a new generation of technology emerged out and they couldn't keep up with it, and consequently lost the game because of their poor performance. Like what happened to the Nokia brand. Introduction of new processor technologies bringing more advanced features in programming languages is an example of kakushin in the filed of software programming. Recent decisions made in Python Steering Council for removal of GIL is another example.

   Some times a Kaikaku might be an intentionally delayed or unintentionally missed part of a previous Kakushin which has eventually paved its way into the product through the force of market or insightfulness of a team member. AnyVer makes distinction between the Kaikaku and Kakushin changes while both are categorized in the **`revolutionary changes`** class.
   
In AnyVer terms, if the devlopment of a new release of a product has just started, it is going to undergo an unstability period of a series of Kaikaku changes until it reaches to the first stable state. At this point of stability after the mentioned series of Kaikaku changes, it has passed a Kakushin era, which as will be discussed later, then its Kakushin number increments once. The amount of the mentioned Kaikaku steps can be any number from 0 to infinity and only when the Kakushin number increments(the stable release gets published), the Kaikaku number will be reset to zero, flaggin the fact that the product's future releases are full stable until the next Kakushin era starts(with an increment in the Kaikaku number which is currently zero).

As discussed earlier, the Kaizen steps don't guarantee full backward-compatibility of the product. They are merely backward-nondestructive. So for a product to achieve full backward-compatibility of its stable release iterations(Kaizen increments), it has to provide a compatibility layer in each release for the downstream products. Kaizen steps on every constant Kaikaku or Kakushin number imply that the product has small non-destructive variations.

**`Pre-release and Post-release`**:
Post-release event is an iteration of products just after the final release, which only contain harmless modifications like corrections documentations etc. AnyVer covers the Post-release as a Kaizen event[(F,P,B)](FPB), and the Pre-release is treated just like in the SemVer Specification. Except for the case of the separator symbol(- in SemVer) for which AnyVer leaves the decision about, based on the implementation situation for the users of the specification. But it must be either "-" or ".". If "." is chosen, then use of "-" is prohibited in the pre-release segment.

**`Build Information`**: 
AnyVer Allows usage of "+" or "." at the end of version number in order to add some information about the build number or local numberings which will be at first place used as an internal informational measure, like that of [Python local numbering](https://packaging.python.org/en/latest/specifications/version-specifiers/#local-version-identifiers) or [SemVers build information](https://semver.org/#spec-item-10).
And if contains a single "-" in the middle of it, what is written before "-" will be called the Branch Name of the product for singnifying a branch of the main product which may later merge back into the main branch or reach to a point of matureness to be rebranded and declared a new product.

**`API`**:
Because what happens behind the scenes has direct effect on the future progress of the product, AnyVer tracks all sorts of variations of a product whether its concerned with the internal development or the public aspects of it. Thus it's necessary for the product to have well defined internal and public APIs.

---
Now its the time to mix things up and make some cool stuff out of the above ideas.
# Summary
Given a version number A.YYYYMMKn.KuFPBR:
1. A is age, started from 0 and incremented annualy.
2. YYYY is the Gregorian year for the last release of the project.
3. MM is the Gregorian month for the last release of the project.(Its zero padded upto 2 digits)
4. Kn is the Kakushin number, started from 0 and incremented every time the products become stable occurance of new Kakushin.(never reset)
5. Ku is the Kaikaku number. started from 0, incremented every time a Kaikaku occures and truncates to 9.(reset to 1 and 0 on every change of A and Kn respectively)
6. F is the number of releases containing functional modifications, starts from 0 and truncates to 9.(reset on every change of A,MM,Kn,Ku)
7. P is the number of releases containing performance upgrades, starts from 0 and truncates to 9.(reset on every change of A,MM,Kn,Ku)
8. B is the number of releases containing bugfixs, starts from 0 and truncates to 9.(reset on every change of A,MM,Kn,Ku)
9. R is the redundant counter, starts from 0 and incremented on every truncation of Ku,F,P and B.(reset on every change of A,MM,Kn,Ku).
R has another role as well. Incrementing R while Ku,F,P are less than value 9, can be used to imply that this release is fully compatible to its corresponding *Kn.Ku\* release.
11. The "0"'s with no number on the right of them until the next segment and no separators on the left, are allowed to be omitted.

**quick example**:    
`0.2024031.1112` (`0.2024031.11120` in full form) is the version number for a product in its not finished first year of development(A=0). This release is published in March, 2024. In this release it has a Kakushin well as a Kaikaku of 1(Kn=Ku=1)(which means it is currently unstable because of Ku>0), and has had one release containing functional modification and performance upgrade(F=P=1) and 2 bugfix(B=2) releases in the current month.    
If in the 4th month of the upcomming year, another version of this product having functional modifications,and performance upgrades and bugfixes gets published, the new release version will be, `1.2025041.1111` (`1.2025041.11110` in full form) but if additionionally there is a Kakushin(the product reached to its stable point) in the mentioned release, the counters for Ku,F,P and B will be reset to zero, Kn will increment once and the version number will be `1.2025042.0` (`1.2025042.00000` in its full form). The upcomming releases will just increament the F,P and B numbers if they are merely Kaizen steps like `1.2025042.0011` for the next release in the same month which containes only bugfixes and performance upgrades. But when the products is going to undergo fundamental changes, then on every release with drastic changes twoards the next stable version, its Kaikaku number will be incremented and this implies that the product is not in fully stable state and the downstream users will experience big-scale disruptions on every release. Although it should rarely happen, but if one or more than one of Ku,F,P and B numbers reach top the 9 number and start truncation, then the Redundant counter will be incremented on every release, e.g. if the B and P numbers in this example start truncation after some more releases in the current month then the version number for the next release will be like `1.2025042.00991`, whith the first Kaizen release in another month the saturated numbers will get reset.

This example illustrates the way AnyVer enables the user to keep track of the products activity during the short and long term time intervals by having a glance of its version number. Because the past big changes in the product and a summary of its timeline are recorded in the first and second parts of the version number. In addition, because of the precedence of the Ku over Kn number in its scheme, AnyVer allowes multiple branches of the product to be released with the same line of version numbering, i.e. A product which is currently in its unstability era with non-zero Kaikaku, can have a release for a previous stable state without affecting the ordering of version numbers, as an example assume for the discussed example which reached to its version number of `1.2025042.00991`, a new Kaikaku release in the similar month, its version number will be `1.20250412.0`.    
Its noteworthy that Redundant counter together with the Kaizen numbers(F,P,B) shows a horizontal backward compatible progress of the product whereas the Kaizen numbers without incrementing the R number still shows a horizontal backward incompatible but progress of the product which is not drastic enough to make big changes in the dependant downstream products. Finally having the Kaikaku number incremented shows a vertical backward incompatible progress which will guide the product to a new stable situation through the subsequent Kaikaku steps.
The last thing to mention is that although R is there to count for truncations of Ku,F,P and B but for a product with more than 9 Kaizen releases a month or 9 Kaikaku releases a year, maybe use of AnyVer is still good idea but it will fail to capture the backward compatible releases from right after the first of the pointed numbers gets saturated, until the next reset of the saturated values.
# Specification
The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in RFC 2119.


# Examples
Some examples...
If you have ...
# Used By
...
# Attributes
Some of the content in this specification is borrowed from the mainstream publicly available specifications like [SemVer](https://semver.org/) and [CalVer](https://calver.org/)
# Contributing
See the [contribution guide](https://github.com/SKhajeh/anyver/blob/main/CONTRIBUTING.MD)
# License
For now its licensed under terms of `CC BY-ND 4.0`. A relicense with more permissive terms is up to come once it matured enough.
