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
I thought this might be 0.
So i did not try to make 100%.
 
**This is my answer in C++ (83%)**
int solution(vector<int> &A) {
    // write your code in C++14 (g++ 6.2.0)
    int nSize = A.size();
    int nPart1 = 0;
    int nPart2 = 0;
    int nMinimum = -1;
    int nTemp = 0;
    for (auto i = 0; i < nSize; ++i)
        nPart2 += A[i];
        
    for (auto j = 0; j < nSize; ++j)
    {
        nPart1 += A[j];
        nPart2 -= A[j];        
        nTemp = abs(nPart1 - nPart2);  
        if (j == 0) nMinimum = nTemp;
        if (nMinimum > nTemp)    nMinimum = nTemp;
        //cout << "nPart 1 : " << nPart1 << ", nPart2 : " << nPart2 << ", A[j] : " << A[j] << ", nTemp : " << nTemp << ", nMinimum : " << nMinimum << endl;
    }
    return nMinimum;
}