---
layout: post
title: Codility Lesson 5-3. Min-Avg-TwoSlice 
tags:
- Codility
---
 Codility Lesson 5-3. Min-Avg-TwoSlice 
<br/><br/>
"1. MinAvgTwoSlice - Find the minimal average of any slice containing at least two elements"
<br/><br/> 
**This is my answer in C++ (100%)**
<br/>int solution(vector&lt;int&gt; &A) {
<br/>&nbsp; &nbsp;    // write your code in C++14 (g++ 6.2.0)
<br/>&nbsp; &nbsp;    double nTemp1 = 0;
<br/>&nbsp; &nbsp;    double nTemp2 = 0;
<br/>&nbsp; &nbsp;    double nMin = 999;
<br/>&nbsp; &nbsp;    int nMinPos = 0;
<br/>&nbsp; &nbsp;    for (auto i = 0; i < A.size() - 2; ++i) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         nTemp1 = (A[i] + A[i + 1]) / 2.0;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         nTemp2 = (A[i] + A[i + 1] + A[i + 2]) / 3.0;        
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (nTemp1 < nMin) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;             nMin = nTemp1;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;             nMinPos = i;
<br/>&nbsp; &nbsp;         }
<br/>&nbsp; &nbsp;         if (nTemp2 < nMin)   {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;             nMin = nTemp2;            
<br/>&nbsp; &nbsp; &nbsp; &nbsp;             nMinPos = i;
<br/>&nbsp; &nbsp;         }        
<br/>&nbsp; &nbsp;         //std::cout << "nMin : " << nMin << ", nMinPos : " << nMinPos << ", i : " << i << std::endl;
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     int nTemp3 = (A[A.size()-1] + A[A.size()-2]) / 2.0;
<br/>&nbsp; &nbsp;     if (nTemp3 < nMin)  {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         nMin = nTemp3;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         nMinPos = A.size() - 2;
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     return nMinPos;
<br/>}