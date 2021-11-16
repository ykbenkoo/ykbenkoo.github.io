---
layout: post
title: DesignPattern - Decorator
tags:
- DesignPattern
---
Decorator
<br/> - Adding behavior without altering the class itself
<br/> - Facilitates the additon of behaviors to individual objects
<br/>
<br/>[Motivation]
<br/> - Want to augment an object with additional functionality
<br/> - Do not want to rewrite or alter existing code (OCP)
<br/> - Want to keep new functionality separate(SRP)
<br/> - Need to be able to interact with existing structures
<br/> - Two options
<br/> : Aggregate the decorated objects
<br/> : Inherit from the decorated object
<br/>
<br/>[Summary]
<br/> - A dynamic decorator keeps the reference to the decorated object(s)
<br/> : ColoredShape{Square{}}
<br/> - A static decorator uses mixin inheritance
<br/> : ColoredShape<Square>
<br/> - Both approaches allow limitless composition
<br/> : TransparentShape<ColoredShape<Cirlce>>
<br/><br/> 
<br/><br/>Here is sample code about decorator pattern
<br/><br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Decorator">View decorater Sample</a>