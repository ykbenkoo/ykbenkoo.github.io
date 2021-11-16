---
layout: post
title: Codility Lesson 2-1. CyclicRotation
tags:
- Codility
---
 Codility Lesson 2-1. CyclicRotation
<br/><br/>
"2-1. CyclicRotation - Rotate an array to the right by a given number of steps."
<br/><br/>
**This is my answer in C++ (100%)**
<br/>vector<int> solution(vector&lt;int&gt; &A, int K) {
<br/>&nbsp; &nbsp;     // write your code in C++14 (g++ 6.2.0)
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     int size = A.size();
<br/>&nbsp; &nbsp;     if (K == 0 || K == size || size <= 1) return A;
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     vector<int> B;
<br/>&nbsp; &nbsp;     int num = K;
<br/>&nbsp; &nbsp;     if (num - size > 0) num = num % size;
<br/>&nbsp; &nbsp;     for (int i = 0; i < size; ++i) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         B.push_back(A[size - num]);
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         num--;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (num <= 0) num = size;
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     return B;    
<br/>}