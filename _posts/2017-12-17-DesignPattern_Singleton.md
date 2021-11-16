---
layout: post
title: DesignPattern - Singleton
tags:
- DesignPattern
---
Singleton
<br/> - A component which is instantiated only once
<br/>
<br/>[Motivation]
<br/> - For some components it only makes sense to have one in the system.
<br/> : Database repository
<br/> : Object factory
<br/> - E.g, the constructor call is expensive
<br/> : We only do it once
<br/> : We provide everyone with the same instance
<br/> - Need to take care of lazy instantiation and thread safety
<br/>
<br/>[Summary]
<br/> - Making a 'safe' singleton is easy
<br/> : Hide or delete the type's constructor, copy constructor and copy assignment operators
<br/> : Create a static method that returns a reference to a static member
<br/> : Guaranted to be thread-safe since C++11
<br/> - Types with 'hard' dependencies on singleton are difficult to test
<br/> : Cannot decouple the singleton and supply a fake object
<br/> - Instead of directly using a singleton, consider depending on an abstraction(e.g, an interface)
<br/> : Consider defining singleton lifetime in DI containner
<br/>Here is sample code about singleton pattern
<br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Singleton">View Singleton Sample</a>