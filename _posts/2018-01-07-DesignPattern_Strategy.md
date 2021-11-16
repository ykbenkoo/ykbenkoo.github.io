---
layout: post
title: DesignPattern - Strategy
tags:
- DesignPattern
---
Strategy
<br/> - System behavior partially specified at runtime
<br/> - Enables the exact behavior of a system to be selected either at run-time(dynamic) or
<br/> compile-time(static)
<br/> - Also known as a policy(esp. in the C++ world)
<br/>
<br/>[Motivation]
<br/> - Many algorithms can be decomposed into higher and lower level part
<br/> - Making tea can be decomposed into
<br/> : The process of making a hot beverage(boil water, pour into cup); and
<br/> : Tea-specific things (put teabag into water)
<br/> - The high-level algorithm can then be reused for making coffee or hot chocolate
<br/> : Supported by beverage-specific strategies
<br/>
<br/>[Summary]
<br/> - Define an algorithm at a high level
<br/> - Define the interface you expect each strategy to follow
<br/> - Provide for either dynamic or static composition of strategy in the overall algorithm
<br/>
<br/>Here is sample code about State pattern
<br/>
<br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Strategy">View Strategy Sample</a>