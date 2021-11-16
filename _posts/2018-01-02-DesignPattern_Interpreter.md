---
layout: post
title: DesignPattern - Interpreter
tags:
- DesignPattern
---
Interpreter
<br/> - A component that processes structured text data.
<br/> - Does so by turning it into separate lexical tokens(lexing)
<br/> - interpreting sequences of said tokens(parsing) 
<br/>
<br/>[Basic idea]
<br/> - Textual input needs to be processed.
<br/> : E.g., turned into OOP structures
<br/> - Some examples
<br/> : Programming language compilers, interpreters and IDEs
<br/> : HTML, XML and similar
<br/> : Numeric expressions (3+4/5)
<br/> : Regular expressions
<br/> - Turning strings into OOP based structures in a complicated process.
<br/>
<br/>[Summary]
<br/> - Barring simple class, an interpreter acts in two stages
<br/> - Lexing turns text into a set of tokens
<br/> : E.g., 3*(4+5) -> Lit[3] Star Lparen Lit[4] Plus Lit[5] Rparen
<br/> - Parsing tokens into meaningful constructs
<br/> : MultiplicationExpression[Integer[3], AdditionExpression[Integer[4], Integer[5]]]
<br/> - Parsed data can then be traversed.
<br/>	
<br/><br/>
<br/>Here is sample code about Interpreter pattern
<br/><br/><a href="https://github.com/korkooyk/CppStudy/tree/master/DesignPattern/Interpreter">View Interpreter Sample</a>