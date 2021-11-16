---
layout: post
title: Codility Lesson 4-1. MissingInteger 
tags:
- Codility
---
 Codility Lesson 4-1. MissingInteger 
<br/><br/>
"4-1. MissingInteger - Find the minimal positive integer not occurring in a given sequence."
<br/><br/> 
**This is my answer in C++ (100%)**
int solution(vector<int> &A) {
    // write your code in C++14 (g++ 6.2.0)
    int nSize = A.size();
    int nMin = 1;
    
    if (nSize == 0) return 1;
    else if (nSize == 1) {
        if (A[0] == 1) return 2;
        return 1;
    }
    
    vector<int> B = A;
    sort(B.begin(), B.end());
    
    for (int i = 0; i < nSize; ++i) {        
        if (B[i] > 0)  {
            if (B[i] == nMin)   nMin++;
            
        }
    }
    if (nMin == 0)  return B[nSize] + 1;
    return nMin;    
}