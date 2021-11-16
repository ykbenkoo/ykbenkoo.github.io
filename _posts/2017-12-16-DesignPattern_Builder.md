---
layout: post
title: DesignPattern - Builder
tags:
- DesignPattern
---
Builder Pattern
<br/>
<br/>Builder pattern is that instead of directly working with one element, we could create a dedicated component.
<br/>this is the core what builder pattern aims.
<br/>insted of constructing the object in a single line of what you're doing is using a specialized component which has the special functions for helping you construct the component.
<br/>And then at some point you just call a function to get whatever it is that you've constructed and work with that
<br/>
<br/>- A builder is a separate componenet for building an object.
<br/>- Can either give builder a constructor or return it via a static function.
<br/>- To make builder fluent, return this.
<br/>- Different facets of an object can be built with different builders working in tandem via a base class
<br/>
<br/>Here is sample code
<br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Builder">View Builder Sample</a>