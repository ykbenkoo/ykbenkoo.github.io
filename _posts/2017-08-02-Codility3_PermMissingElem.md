---
layout: post
title: Codility Lesson 3-1. PermMissingElem 
tags:
- Codility
---
 Codility Lesson 3-1. PermMissingElem 
<br/><br/>
"3-1. PermMissingElem - Find the missing element in a given permutation."
<br/><br/>
**This is my answer in C++ (100%)**
<br/>int solution(vector&lt;int&gt; &A) {
<br/>&nbsp; &nbsp;     // write your code in C++14 (g++ 6.2.0)
<br/>&nbsp; &nbsp;     int nSize = A.size();
<br/>&nbsp; &nbsp;    if (nSize <= 0)     return 1; 
<br/>&nbsp; &nbsp;        
<br/>&nbsp; &nbsp;     nSize ++;
<br/>&nbsp; &nbsp;     int nSum = (nSize / 2) * (nSize + 1);    
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     if (nSize == 1) nSum++;
<br/>&nbsp; &nbsp;     if (nSize % 2)  nSum += (nSize / 2) + 1;
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     for (auto i = 0; i < nSize - 1 ; ++i) {
<br/>&nbsp; &nbsp;  &nbsp; &nbsp;        nSum -= A[i];
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;         
<br/>&nbsp; &nbsp;     return nSum;
<br/>}