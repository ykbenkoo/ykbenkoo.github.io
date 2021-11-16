---
layout: post
title: Codility Lesson 6-3. MaxProductOfThree
tags:
- Codility
---
 Codility Lesson 6-3. MaxProductOfThree
<br/><br/>
"1. MaxProductOfThree - Maximize A[P] * A[Q] * A[R] for any triplet (P, Q, R)"
<br/>
<br/> 
<br/>**This is my answer in C++ (100%).**
<br/>#include <algorithm>
<br/>int solution(vector&lt;int&gt; &A) {
<br/>&nbsp; &nbsp;     // write your code in C++14 (g++ 6.2.0)
<br/>&nbsp; &nbsp;     vector&lt;int&gt; B(A);
<br/>&nbsp; &nbsp;     sort(B.begin(), B.end());
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;    int nSize = B.size();
<br/>&nbsp; &nbsp;     int nCheckMin = B[0] * B[1] * B[nSize -1];
<br/>&nbsp; &nbsp;     int nCheckPlu = B[nSize - 2] * B[nSize - 1] * B[nSize - 3];
<br/>&nbsp; &nbsp;     if (B[nSize - 1] <= 0)          return B[nSize - 1] * B[nSize - 2] * B[nSize - 3];
<br/>&nbsp; &nbsp;     else if (nCheckMin > nCheckPlu) return nCheckMin;
<br/>&nbsp; &nbsp;     else                            return nCheckPlu;
<br/>}   