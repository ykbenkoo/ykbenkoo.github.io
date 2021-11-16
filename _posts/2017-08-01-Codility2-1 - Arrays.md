---
layout: post
title: Codility Lesson 2-2. OddOccurrencesInArray 
tags:
- Codility
---
 Codility Lesson 2-2. OddOccurrencesInArray 
<br/><br/>
"2-2. OddOccurrencesInArray - Find value that occurs in odd number of elements."
<br/><br/>
**This is my answer in C++ (100%)**
It was quite simple if you know exclusive logic.
// you can use includes, for example:
// #include <algorithm>

// you can write to stdout for debugging purposes, e.g.
// cout << "this is a debug message" << endl;

int solution(vector<int> &A) {
    // write your code in C++14 (g++ 6.2.0)    
    int ret = 0;
    for (auto i = 0; i < A.size(); ++i)
    {
        ret ^= A[i];
    }
    return ret;
}