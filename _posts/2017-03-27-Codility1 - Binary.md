---
layout: post
title: Codility Lesson 1. Binary
tags:
- Codility
---
 Codility Lesson 1, Binary Gap
<br/><br/>
"1. BinaryGap : returns the maximum number of zeros in a binary number."
<br/><br/>
**This is my answer in C (100%)**
int solution(int N) {
    // write your code in C++14 (g++ 6.2.0)
    int nOneCount = 0;
    int nCount = 0;
    int nMaxCount = 0;
    while (N) {
        if (N % 2) { 
         if (nMaxCount < nCount) nMaxCount = nCount;
         nCount = 0;
         nOneCount++;
        }
        else if (nOneCount) nCount++;
        N = N / 2;
    }
    return nMaxCount;
}
