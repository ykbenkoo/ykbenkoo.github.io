---
layout: post
title: Codility Lesson 2-2. OddOccurrencesInArray 
tags:
- Codility
---
 Codility Lesson 2-2. OddOccurrencesInArray 
<br/><br/>
"2-2. OddOccurrencesInArray - Find value that occurs in odd number of elements."
<br/><br/>
**This is my answer in C++ (100%)**
<br/>It was quite simple if you know exclusive logic.
<br/>// you can use includes, for example:
<br/>// #include <algorithm>
<br/>
<br/>// you can write to stdout for debugging purposes, e.g.
<br/>// cout << "this is a debug message" << endl;
<br/>
<br/>int solution(vector&lt;int&gt; &A) {
<br/>&nbsp; &nbsp;    // write your code in C++14 (g++ 6.2.0)    
<br/>&nbsp; &nbsp;     int ret = 0;
<br/>&nbsp; &nbsp;     for (auto i = 0; i < A.size(); ++i)
<br/>&nbsp; &nbsp;     {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         ret ^= A[i];
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     return ret;
<br/>}