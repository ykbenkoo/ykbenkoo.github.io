---
layout: post
title: Boost - Compile error(yyacc.c)
tags:
- Boost
---
Boost - Compile error
<br/> - 'yyacc.c': No such file or directory
<br/>
<br/>When we met this error message, We do not know how to solve this problem.
<br/>I found it on google.com
<br/>Here is the method to solve this
<br/>
<br/>1) cd to "<boost base directory>\tools\build\src\engine"
<br/>
<br/>2) Execute: "set VSCMD_START_DIR=%CD%"
<br/>
<br/>3) cd to "<boost base directory>"
<br/>
<br/>4) Execute: bootstrap
<br/>
<br/>5) Execute: "set VSCMD_START_DIR=" (be sure there is no space after =)
<br/>
<br/>6) Execute: b2
<br/>
<br/>(based on solution: ?https://github.com/boostorg/build/issues/236#issuecomment-330475306)