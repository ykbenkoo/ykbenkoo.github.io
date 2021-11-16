---
layout: post
title: DesignPattern - Observer
tags:
- DesignPattern
---
Observer
<br/> - Getting notification when things changed.
<br/> - An observer is an object that wishes to be informed about events happening in the system
<br/> - The entity generating the events is an observable
<br/>
<br/>[Motivation]
<br/> - We need to be informed when certain things happen
<br/> : Object's field changes
<br/> : Object does something
<br/> : Some external evernt occurs
<br/> - We want to listen to events and notified when they occur
<br/> - Terminology
<br/> : event and subscriber
<br/> : signal and slot (Boost, Qt, etc.)
<br/>
<br/>[Summary]
<br/> - Two participants
<br/> : Observer provides a way of subscribing to an event(signal)
<br/> : Observable performs the subscription
<br/> - Observable implementation is always intrusive (observer doesn't need to be)
<br/> - Multithread/reentrant use can cause issues
<br/> - Ready-made implementations of Observer are available
<br/><br/>
<br/><br/>Here is sample code about Observer pattern
<br/><br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Observer">View Observer Sample</a>