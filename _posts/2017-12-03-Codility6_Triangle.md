---
layout: post
title: Codility Lesson 6-1. Triangle
tags:
- Codility
---
 Codility Lesson 6-1. Triangle
<br/><br/>
"1. Triangle - Determine whether a triangle can be built from a given set of edges."
<br/>
<br/> 
<br/>**This is my answer in C++ (100%).**
<br/>#include <algorithm>
<br/>int solution(vector&lt;int&gt; &A) {
<br/>&nbsp; &nbsp;     // write your code in C++14 (g++ 6.2.0)
<br/>&nbsp; &nbsp;     vector&lt;int&gt; B(A);
<br/>&nbsp; &nbsp;     sort(B.begin(), B.end());
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     if (B.size() <= 2)  return 0;
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     for (auto i = 0; i < B.size() - 2 ; ++i) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (B[i+2] - B[i+1] < B[i]) return 1; 
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;    return 0;
<br/>}   