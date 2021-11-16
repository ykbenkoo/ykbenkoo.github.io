---
layout: post
title: Codility Lesson 3-1. PermMissingElem 
tags:
- Codility
---
 Codility Lesson 3-1. PermMissingElem 
<br/><br/>
"3-1. PermMissingElem - Find the missing element in a given permutation."
<br/><br/>
**This is my answer in C++ (100%)**
int solution(vector<int> &A) {
    // write your code in C++14 (g++ 6.2.0)
    int nSize = A.size();
    if (nSize <= 0)     return 1; 
        
    nSize ++;
    int nSum = (nSize / 2) * (nSize + 1);    
    
    if (nSize == 1) nSum++;
    if (nSize % 2)  nSum += (nSize / 2) + 1;
    
    for (auto i = 0; i < nSize - 1 ; ++i) {
        nSum -= A[i];
    }
        
    return nSum;
}