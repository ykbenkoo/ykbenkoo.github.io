---
layout: post
title: DesignPattern - Template
tags:
- DesignPattern
---
Template Method
<br/> - It allows us to define the 'skeleton' of the algorithm with concrete implementations
<br/> defined in subclasses
<br/>
<br/>[Motivation]
<br/> - Algorithms can be decomposed into common parts + specifics
<br/> - Strategy pattern does this through composition
<br/> : High-level algorithm uses an interface
<br/> : Concrete implementations implement the interface
<br/> - Template Method does the same thing through inheritance
<br/> : Overall algorithm makes use of abstract member
<br/> : Inheritors override the abstract members
<br/> : Parent template method invoked
<br/>
<br/>[Summary]
<br/> - Define an algorithm at a high level
<br/> - Define constituent parts as abstract methods
<br/> - Inherit the algorithm class, providing necessary overrides
<br/>
<br/>Here is sample code about Template pattern
<br/>
<br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Template">View Template Sample</a>