---
layout: post
title: DesignPattern - Flyweight
tags:
- DesignPattern
---
Flyweight
<br/> - A space optimization technique that lets us use less memory by sotring externally 
<br/>  the data associated with similar objects
<br/>
<br/>[Motivation]
<br/> - Avoid redundancy when storing data
<br/> - E.g., MMORPG
<br/> : Plenty of users with identical first/last names
<br/> : No sense in storing same first/last name over and over again
<br/> : Store a list of names and pointers to them
<br/> - E.g., bold or italic text in the console
<br/> : Don't want each character to have a formatting character
<br/> : Operate on ranges (e.g., line number, start/end pointer)
<br/>
<br/>[Summary]
<br/> - Store common data externally
<br/> : E.g., static map
<br/> - Define the idea of 'ranges' on homogeneous collections
<br/> : Store data related to thoese ranges
<br/><br/>
<br/>Here is sample code about flyweight pattern
<br/><br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Flyweight">View Flyweight Sample</a>