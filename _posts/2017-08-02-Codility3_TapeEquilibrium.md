---
layout: post
title: Codility Lesson 3-2. FrogJmp
tags:
- Codility
---
 Codility Lesson 3-2. FrogJmp
<br/><br/>
"3-2. FrogJmp - Count minimal number of jumps from position X to Y."
<br/><br/>
I did not understand this question. why [-1000, 1000]'s result is 2000?
<br/>I thought this might be 0.
<br/>So i did not try to make 100%.
<br/> 
<br/>**This is my answer in C++ (83%)**
<br/>int solution(vector&lt;int&lt; &A) {
<br/>&nbsp; &nbsp;     // write your code in C++14 (g++ 6.2.0)
<br/>&nbsp; &nbsp;     int nSize = A.size();
<br/>&nbsp; &nbsp;     int nPart1 = 0;
<br/>&nbsp; &nbsp;     int nPart2 = 0;
<br/>&nbsp; &nbsp;     int nMinimum = -1;
<br/>&nbsp; &nbsp;     int nTemp = 0;
<br/>&nbsp; &nbsp;     for (auto i = 0; i < nSize; ++i)
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         nPart2 += A[i];
<br/>&nbsp; &nbsp;         
<br/>&nbsp; &nbsp;     for (auto j = 0; j < nSize; ++j)
<br/>&nbsp; &nbsp;     {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         nPart1 += A[j];
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         nPart2 -= A[j];        
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         nTemp = abs(nPart1 - nPart2);  
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (j == 0) nMinimum = nTemp;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (nMinimum > nTemp)    nMinimum = nTemp;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         //cout << "nPart 1 : " << nPart1 << ", nPart2 : " << nPart2 << ", A[j] : " << A[j] << ", nTemp : " << nTemp << ", nMinimum : " << nMinimum << endl;
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     return nMinimum;
<br/>}