---
layout: post
title: Codility Lesson 6-2. Distinct
tags:
- Codility
---
 Codility Lesson 6-2. Distinct
<br/><br/>
"1. Distinct - Compute number of distinct values in an array."
<br/>
<br/> 
<br/>**This is my answer in C++ (100%).**
<br/>#include <algorithm>
<br/>int solution(vector&lt;int&gt; &A) {
<br/>&nbsp; &nbsp;     // write your code in C++14 (g++ 6.2.0)
<br/>&nbsp; &nbsp;     if (A.size() <= 0)  return 0;
<br/>&nbsp; &nbsp;     vector<int> B(A);
<br/>&nbsp; &nbsp;     sort(B.begin(), B.end());
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     int nCnt = 1;
<br/>&nbsp; &nbsp;     int nTemp = B[0];
<br/>&nbsp; &nbsp;     for (auto i = 0; i < B.size(); ++i) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (nTemp != B[i]) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;             nCnt++;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;             nTemp = B[i];
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         }
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     return nCnt;
<br/>}   