---
layout: post
title: Codility Lesson 4-2. PermCheck 
tags:
- Codility
---
 Codility Lesson 4-2. PermCheck 
<br/><br/>
"4-2. PermCheck - Check whether array A is a permutation."
<br/><br/> 
**This is my answer in C++ (100%)**
// you can use includes, for example:
#include <algorithm>

// you can write to stdout for debugging purposes, e.g.
// cout << "this is a debug message" << endl;

int solution(vector<int> &A) {
    // write your code in C++14 (g++ 6.2.0)
    if (A.size() <= 0)      return 1;
    else if (A.size() == 1 && A[0] == 1)    return 1;
    
    vector<int> B = A;
    sort(B.begin(), B.end());
    
    for (auto i = 0; i < B.size(); ++i) {
        if (B[i] != i + 1)
            return 0;
    }
    return 1;
}