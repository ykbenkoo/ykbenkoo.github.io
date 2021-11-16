---
layout: post
title: DesignPattern - Chain of Responsibility
tags:
- DesignPattern
---
Chain of Responsibility
<br/> - Sequence of handlers processing an event one after another
<br/> - A chain of components who all get a chance to process a command or a query,
<br/> optionally having default processing implementation and an ability to terminate
<br/> the processing chain.
<br/>[Motivation]
<br/> - Unethical behavior by an employee; who takes the blame?
<br/> : Employee
<br/> : Manager
<br/> : CEO
<br/> - You click a graphical element on a form
<br/> : Button handles it, stops further processing
<br/> : Underlying group box
<br/> : Underlying window
<br/> - CCG computer game
<br/> : Creature has attack and defense value
<br/> : Those can be boosted by other cards
<br/> 
<br/>[Summary]
<br/> - CoR can be implemented as
<br/> : A chain of pointers/references(singly liked list)
<br/> : Centralized list
<br/> - Enlist objects in the chain, possibly controlling their order
<br/> - Object removal from chain (e.g., disconnect from a signal)
<br/>
<br/><br/>
<br/>Here is sample code about CoR pattern
<br/><br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/CoR">View CoR Sample</a>