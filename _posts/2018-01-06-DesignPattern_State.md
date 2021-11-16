---
layout: post
title: DesignPattern - State
tags:
- DesignPattern
---
State
<br/> - A pattern in which the object's behavior is determined by its state
<br/> - An object transitions from one state to another (something needs to trigger a transition)
<br/> - A formalized construct which manages state and transitions is called a state machine.
<br/>
<br/>
<br/>[Motivation]
<br/> - Consider an ordinary telephone
<br/> - What you do with it depends on the state of the phone/line
<br/> : If it's ringing or you want to make a call, you can pick it up
<br/> : Phone must be off the hook to talk/make a call
<br/> : If you try calling someone, and it's busy, you put the handset down
<br/> - Changes in state can be explicit or in response to event(Observer pattern)
<br/>
<br/>[Summary]
<br/> - Given sufficient complexity, it pays to formally define possible states and events/triggers
<br/> - Can define
<br/> : State entry/exit behaviors
<br/> : Action when a particular event causes a transition
<br/> : Guard conditions enabling/disabling a transition
<br/> : Default action when no transitions are found for an event
<br/>
<br/>
<br/>Here is sample code about State pattern
<br/>
<br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/State">View State Sample</a>