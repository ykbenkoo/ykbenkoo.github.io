---
layout: post
title: Codility Lesson 5-1. PCountDiv
tags:
- Codility
---
 Codility Lesson 5-1. CountDiv
<br/><br/>
"5-1. CountDiv - Compute number of integers divisible by k in range [a..b]"
<br/><br/> 
**This is my answer in C++ (100%)**
<br/> int solution(int A, int B, int K) {
<br/>&nbsp; &nbsp;     // write your code in C++14 (g++ 6.2.0)
<br/>&nbsp; &nbsp;     if (A == B) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (A % K == 0) return 1;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         else return 0;
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     if (B < K) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (A <= 0) return 1; //I dont understand why Codility deals with 0 which divides everything.
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         else return 0;
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     if (B - A < K && B > K) {        
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         return 1;
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     // for the precison answer
<br/>&nbsp; &nbsp;     if (A % K) A = A + (K - (A % K));
<br/>&nbsp; &nbsp;     if (B % K) B = B - (B % K);
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     return (B - A) / K + 1;         
<br/> } 