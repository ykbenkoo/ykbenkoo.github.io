---
layout: post
title: DesignPattern - Command
tags:
- DesignPattern
---
Command
<br/> - An object which represents an instruction to perform a particular action
<br/> - Contains all the information necessary for the action to be taken
<br/>
<br/>[Motivation]
<br/> - Ordinary C++ statements are perishable
<br/> : Cannot undo a field/property assignment
<br/> : Cannot directly serialize a sequence of actions (calls)
<br/> - Want an object that represents an operation
<br/> : X should change its field Y to the value Z
<br/> : X Should do W()
<br/> - Uses: GUI commands, multi-level undo/redo, macro recording and more!
<br/>
<br/>[Command Query Separation]
<br/> - Command = asking for an action or change (e.g., please set your attack value to 2)
<br/> - Query = asking for information (e.g., please give me your attack value)
<br/> - CQS = having separate means of sending commands and queries.
<br/> - In GoF context, both commands and queries are represented with the Command design pattern.
<br/>
<br/>[Summary]
<br/> - Encapsulate all details of an operation in a separate object
<br/> - Define instruction for applying the command (either in the command it self, or elsewhere)
<br/> - Optionally define instructions for undoing the command
<br/> - Can create composite commands (a.k.a macros)
<br/><br/>
<br/>Here is sample code about Command pattern
<br/><br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Command">View Command Sample</a>