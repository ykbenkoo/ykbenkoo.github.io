---
layout: post
title: Codility Lesson 4-1. MissingInteger 
tags:
- Codility
---
 Codility Lesson 4-1. MissingInteger 
<br/><br/>
"4-1. MissingInteger - Find the minimal positive integer not occurring in a given sequence."
<br/><br/> 
**This is my answer in C++ (100%)**
<br/>int solution(vector&lt;int&gt; &A) {
<br/>&nbsp; &nbsp;    // write your code in C++14 (g++ 6.2.0)
<br/>&nbsp; &nbsp;     int nSize = A.size();
<br/>&nbsp; &nbsp;     int nMin = 1;
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     if (nSize == 0) return 1;
<br/>&nbsp; &nbsp;     else if (nSize == 1) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (A[0] == 1) return 2;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         return 1;
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     vector&lt;int&gt; B = A;
<br/>&nbsp; &nbsp;     sort(B.begin(), B.end());
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     for (int i = 0; i < nSize; ++i) {        
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (B[i] > 0)  {
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;             if (B[i] == nMin)   nMin++;            
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         }
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     if (nMin == 0)  return B[nSize] + 1;
<br/>&nbsp; &nbsp;     return nMin;    
}