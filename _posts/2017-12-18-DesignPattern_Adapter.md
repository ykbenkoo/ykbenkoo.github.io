---
layout: post
title: DesignPattern - Adapter
tags:
- DesignPattern
---
Adapter
<br/> - Getting the interface you want from the interface you have
<br/> - A construct which adapts an existing interface X to conform to the required interface Y.
<br/>
<br/>[Summary]
<br/> - Implementing an Adapter is easy.
<br/> - Determin the API you have and the API you need
<br/> - Create a component which aggregates (has a reference to, ...) the adaptee
<br/> - Intermediate representations can pile up: use caching and other optimizations
<br/>
<br/>Here is sample code about adapter pattern
<br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Adapter">View Adapter Sample</a>