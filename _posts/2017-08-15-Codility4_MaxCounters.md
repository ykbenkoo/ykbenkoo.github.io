---
layout: post
title: Codility Lesson 4-4. MaxCounters
tags:
- Codility
---
 Codility Lesson 4-4. MaxCounters 
<br/><br/>
"4-4. MaxCounters - Calculate the values of counters after applying all alternating operations: increase counter by 1; set value of all counters to current maximum."
<br/><br/> 
**This is my answer in C++ (100%)**
<br/>vector<int> solution(int N, vector&lt;int&gt; &A) {
<br/>&nbsp; &nbsp;     // write your code in C++14 (g++ 6.2.0)
<br/>&nbsp; &nbsp;     vector&lt;int&gt; B(N, 0);
<br/>&nbsp; &nbsp;     int nCurrMax = 0;
<br/>&nbsp; &nbsp;     int nMax = 0;
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     for (auto &i : A) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (i > N)  nCurrMax = nMax;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         else {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;             if (B[i-1] < nCurrMax)  B[i-1] = nCurrMax + 1;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;             else B[i-1]++;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;             
<br/>&nbsp; &nbsp; &nbsp; &nbsp;             if (nMax < B[i-1])  nMax = B[i-1];
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         }
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     for (auto &j : B) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (j < nCurrMax)   j = nCurrMax;
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     return B;
<br/>}