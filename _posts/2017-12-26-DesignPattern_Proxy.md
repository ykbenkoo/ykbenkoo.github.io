---
layout: post
title: DesignPattern - Proxy
tags:
- DesignPattern
---
Proxy
<br/> - An interface for accessing a particular resource
<br/> - A class that functions as an interface to a particular resource.
<br/> That resource may be remote, expensive to construct, or may require
<br/> logging or some other functionality
<br/>
<br/>[Motivatoin]
<br/> - You are calling foo.bar()
<br/> - This assumes that foo is in the same process as bar()
<br/> - What if, later on, you want to put all Foo-related operations into a separate process
<br/> : Can you avoid changing your code?
<br/> - Proxy to the rescue!
<br/> : Same interface, entirely different behavior
<br/> - This is called a communication proxy
<br/> : Other types:logging, virtual, guarding, ...
<br/>
<br/>[Proxy vs Decorator]
<br/> - Proxy provides an identical interface
<br/> - Decorator provides an enhanced interface
<br/> - Decorator typically aggregates(or has reference) what it is decorating; proxy doesn't have to
<br/> - Proxy might not even be working with a materialized object
<br/>
<br/>[Summary]
<br/> - A proxy has the same interface as the underlying object
<br/> - To creat a proxy, simply replicate the existing interface of an object
<br/> - Add relevant functionality to the redefined member functions.
<br/> - Different proxies (communication, logging, caching, etc.) have completely different behaviors
<br/>
<br/>Here is sample code about proxy pattern
<br/><br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Proxy">View Proxy Sample</a>