---
layout: post
title: DesignPattern - Facade
tags:
- DesignPattern
---
Facade
<br/> - Exposing several components through a single interface
<br/> - Provides a simple, easy to understand/user interface over a large and sophisticated body of code.
<br/>[Motivation]
<br/> - Balancing complexity and presentation/usability
<br/> - Typical home
<br/> : Many subsystems(electrical, sanitation)
<br/> : Complex internal structure(e.g, floor layers)
<br/> : End user is not exposed to internals
<br/> - Same with software
<br/> : Many systems working to provied flexibility, but..
<br/> : API consumers want it to 'just work'
<br/>
<br/>[Summary]
<br/> - Build a facade to provide a simplified API over a set of class
<br/> - Many wish to (optionally) expose internals through the facade
<br/> - May allow users to 'escalate' to use more complex APIs if they need to
<br/>
<br/><br/><br/> 
<br/><br/>Here is sample code about facade pattern
<br/><br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Facade">View facade Sample</a>