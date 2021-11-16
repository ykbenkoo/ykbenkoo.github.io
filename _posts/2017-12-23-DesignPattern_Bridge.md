---
layout: post
title: DesignPattern - Bridge
tags:
- DesignPattern
---
Bridge
<br/> - Connecting components together through abstractions.
<br/> - A mechanism that decouples an interfacce (hierarchy) from an implementation(hierarchy)
<br/> 
<br/>[Motivation]
<br/> - Bridge prevents a 'Cartesian product' complexity explosion
<br/> - Example
<br/> : Base class ThreadScheduler
<br/> : Can be preemptive or cooperative
<br/> : Can run or Windows or Linux
<br/> : End up with a 2x2 scenario : WindowsPTS, UnixPTS, WindowsCTS, UnixCTS
<br/> - Bridge pattern avoids the entity explosion
<br/>
<br/>[Summary]
<br/> - Decouple abstraction from implementation
<br/> - Both can exist as hierarchies 
<br/> - A stronger form of encapsulation
<br/> 
<br/><br/>Here is sample code about bridge pattern
<br/><br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Bridge">View Bridge Sample</a>