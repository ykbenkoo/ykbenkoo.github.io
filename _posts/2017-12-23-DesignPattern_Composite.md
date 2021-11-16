---
layout: post
title: DesignPattern - Composite
tags:
- DesignPattern
---
Composite
<br/> - A mechanism for Treating individual(scalar) and aggregate objects uniformly
<br/> 
<br/>[Motivation]
<br/> - Objects use other objects's fields/properties/member through inheritance and composition
<br/> - Composition lets us make compound objects
<br/> : E.g, a mathematical expression composed of simple expressions; or
<br/> : A grouping of shapes that consists of several shapes
<br/> - Composite design pattern is used to treat both single(scalar) and composite objects uniformly
<br/> : I.e, Foo and Collection<Foo> have common APIs
<br/>
<br/>[Summary]
<br/> - Objects can use other objects via inheritance/composition
<br/> - Some composed and singular objects need similar/identical behaviors
<br/> - Composite design pattern lets us treat both types of objects uniformly
<br/> - C++ uses duck typing, expecting enumerable types to provide begin()/end()
<br/> - A single object can masquerable as a collectoin
<br/> : Foo * begin() { return this; }
<br/> : Foo * end()   { return this+1; }
<br/><br/> 
<br/><br/>Here is sample code about composite pattern
<br/><br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Composite">View composite Sample</a>