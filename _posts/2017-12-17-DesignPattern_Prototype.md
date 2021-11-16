---
layout: post
title: DesignPattern - Prototype
tags:
- DesignPattern
---
Prototype 
<br/> - A partially or fully initialized object that you copy(clone) and make use of
<br/>
<br/>[Motivation]
<br/> - Complicated objects (e.g., cars) are not designed from scratch 
<br/> : They reiterate existing designs
<br/> - An existing (partially or fully constructed) design is a Prototype
<br/> - We make a copy (clone) the prototype and customize it
<br/> : Requires 'deep copy' support
<br/> - We make the cloning convenient (e.g. via a factory)
<br/>
<br/>[Summary]
<br/> - To implement a prototype partially construct an object and store it somewhere.
<br/> - Clone the prototype
<br/> : Implement your own deep copy functionally or
<br/> : Serialize and deserialize
<br/>Here is sample code about prototype pattern
<br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Prototype">View Prototype Sample</a>