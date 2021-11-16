---
layout: post
title: DesignPattern - Iterator
tags:
- DesignPattern
---
Iterator
<br/> - An ob ject that facilitates the traversal of a data structure
<br/>[Motivation]
<br/> - Iteration(traversal) is a core functionality of various data structures
<br/> - An iterator is a class that facilitates the traversal
<br/> : Keep a reference to the current element
<br/> : Knows how to move to a different element
<br/> - Can be used implicitly
<br/> : Range-based for
<br/> : Coroutines
<br/>
<br/>[Summary]
<br/> - An object can be iterated (traversed) if it defines a.begin()/end() pair
<br/> - An iterator specified how you can traverse an object
<br/> - Typically requires of != and ++ operators
<br/> - ++ is called sporadically, so cannot be recursive, but..
<br/> - Coroutines allow recursion through generator-yielding functions
<br/>
<br/><br/>
<br/>Here is sample code about Interpreter pattern
<br/><br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Iterator">View Iterator Sample</a>