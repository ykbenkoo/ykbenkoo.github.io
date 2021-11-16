---
layout: post
title: Codility Lesson 5-2. PassingCars 
tags:
- Codility
---
 Codility Lesson 5-2. PassingCars 
<br/><br/>
"5-2. PassingCars - Count the number of passing cars on the road."
<br/><br/> 
**This is my answer in C++ (100%)**
<br/>int solution(vector&lt;int&gt; &A) {
<br/>&nbsp; &nbsp;     // write your code in C++14 (g++ 6.2.0)    
<br/>&nbsp; &nbsp;     /****** This code was time-limited.
<br/>&nbsp; &nbsp;     for (auto iter = A.begin(); iter != A.end(); ++iter) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (*iter == 0) {            
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;             nSum += count_if(iter, A.end(), [](int & n){ return n == 1; });            
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         }
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     *********/
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;     vector&lt;int&gt; B;
<br/>&nbsp; &nbsp;     int nSum = 0;
<br/>&nbsp; &nbsp;     int nASize = A.size();
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     if (nASize <= 1) return 0;
<br/>&nbsp; &nbsp;     for (auto i = 0; i < nASize; ++i)
<br/>&nbsp; &nbsp;     {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;        if (A[i] == 0) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;             B.push_back(i);
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         }
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     int nBSize = B.size();
<br/>&nbsp; &nbsp;     if (nBSize <= 0) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         return 0;
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     else if (nBSize == 1){
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (B[0] < nASize)  return nASize - B[0] - 1;
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     else {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         for (auto j = 0; j < nBSize - 1; ++j)
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         {
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;             nSum += (B[j+1] - B[j] - 1) * (j + 1);
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;             if (j == nBSize - 2)  {
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;                 nSum += (nASize - (B[j+1] + 1)) * nBSize; 
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;             }
<br/>&nbsp; &nbsp; &nbsp; &nbsp;        }        
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     if (nSum < 0 || nSum > 1000000000)  return -1;
<br/>&nbsp; &nbsp;     return nSum;
<br/>}