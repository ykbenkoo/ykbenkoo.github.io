---
layout: post
title: DesignPattern - Mediator
tags:
- DesignPattern
---
Mediator
<br/> - A component that facilitates communication between other components without them
<br/> necessarily being aware of each other or having direct (reference) access to each other.
<br/>
<br/>[Motivation]
<br/> - Components may go in and out of a system at any time
<br/> : Chat room participants
<br/> : Players in an MMORPG
<br/> - It makes no sense for them to have direct references to one another
<br/> : Those references may go dead
<br/> - Solution: Have then all refer to some central component that faclitates communication
<br/>
<br/>[Summary]
<br/> - Craete the mediator and have each object in the system refer to it
<br/> : E.g., in a field
<br/> - Mediator engages in bidirectional communication with its connected components
<br/> - Mediator has functions the components can call
<br/> - Components have functions the mediator can call
<br/> - Even processing (e.g., Rx) libraries make communication easier to implement
<br/><br/>
<br/><br/>Here is sample code about Mediator pattern
<br/><br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Mediator">View Mediator Sample</a>