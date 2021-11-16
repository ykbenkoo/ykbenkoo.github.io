---
layout: post
title: DesignPattern - Visitor
tags:
- DesignPattern
---
Visitor
 - Typically a tool for structure traversal rather than anything else.
 - A pattern where a component (visitor) is allowed to raverse the entire inheritance hierarchy
 - Implemented by propagating a single visit() method throughout the entire hierarchy.

[Motivation]
 - Need to define a new operation on an entire class hierarchy
 : E.g., make a document model printable to HTML/Markdown
 - Do not want to keep modifying every class in the hierarchy
 - Need access to the non-common aspects of classes in the hierarchy
 : Cannot put everything into a single interface
 - Create an external component to handle rendering
 : But preferably avoid type checks

[Summary]
 - Propagate an accept(visitor *v) method throughout the entire hierarchy
 - Create a visitor with visit(Foo *) visit(Bar *), ... for each element in the hierarchy
 - Each accept() simply calls visitor.visit(this)
 
Here is sample code about Visitor pattern

<a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Visitor">View Visitor Sample</a>