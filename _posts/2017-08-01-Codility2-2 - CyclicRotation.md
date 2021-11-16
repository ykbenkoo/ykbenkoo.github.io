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
vector<int> solution(vector<int> &A, int K) {
    // write your code in C++14 (g++ 6.2.0)
    
    int size = A.size();
    if (K == 0 || K == size || size <= 1) return A;
    
    vector<int> B;
    int num = K;
    if (num - size > 0) num = num % size;
    for (int i = 0; i < size; ++i) {
        B.push_back(A[size - num]);
        num--;
        if (num <= 0) num = size;
    }
    return B;    
}