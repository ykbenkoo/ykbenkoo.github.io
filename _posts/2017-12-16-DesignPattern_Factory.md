---
layout: post
title: DesignPattern - Factory
tags:
- DesignPattern
---
Factory Pattern
<br/> - A component respoinsible soley for the wholesale (not piecewise) creation of objects.
<br/>
<br/>[Motivation]
<br/>Object creation logic becomes too convoluted.
<br/>Constructor is not descriptive
<br/> - Name mandated by name of containing type.
<br/> - Cannot overload with same sets of arguments with different names
<br/> - Can turn into 'optional parameter hall'
<br/>Object creation(non-piecewise, unlike Builder) can be outsourced to
<br/> - A separate function(Factory Method)
<br/> - That may exist in a separate class(Factory)
<br/> - Can create hierarch of factory with abstract factory
<br/>
<br/>[Summary]
<br/> - A factory method is a static method that creats objects
<br/> - A factory can take care of object creation
<br/> - A factory can be external or reside inside the object as an inner class
<br/> - Hirerchies of factories can be used to create related objects.
<br/>
<br/>Here is sample code about factory pattern
<br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Factory">View Factory Sample</a>