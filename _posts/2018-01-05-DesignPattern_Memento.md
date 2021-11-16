---
layout: post
title: DesignPattern - Memento
tags:
- DesignPattern
---
Memento
<br/> - A token/handle representing the system state.
<br/> - Lets us roll back to the state when the token was generated. 
<br/> - May or may not directly expose state information
<br/>
<br/>[Motivation]
<br/> - An object or system goes through changes
<br/> : E.g., a bank account gets deposits and withdrawals
<br/> - There are different ways of navigating those changes
<br/> - One way is to record every change (Command) and teach a command to 'undo' itself
<br/> - Another is to simply save snapshots of the system.
<br/>
<br/>[Summary]
<br/> - Mementos are used to roll back states arbitrarily
<br/> - A memento is simply a token/handle class with (typically) no functions of its own
<br/> - A memento is not required to expose directly the state(s) to which it reverts the system.
<br/> - Can be used to implement undo/redo
<br/><br/>
<br/><br/>Here is sample code about Memento pattern
<br/><br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Memento">View Memento Sample</a>