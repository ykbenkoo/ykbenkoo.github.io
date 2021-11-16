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
int solution(int A, int B, int K) {
    // write your code in C++14 (g++ 6.2.0)
    if (A == B) {
        if (A % K == 0) return 1;
        else return 0;
    }
    if (B < K) {
        if (A <= 0) return 1; //I dont understand why Codility deals with 0 which divides everything.
        else return 0;
    }
    
    if (B - A < K && B > K) {        
        return 1;
    }
    
    // for the precison answer
    if (A % K) A = A + (K - (A % K));
    if (B % K) B = B - (B % K);
    
    return (B - A) / K + 1;         
} 