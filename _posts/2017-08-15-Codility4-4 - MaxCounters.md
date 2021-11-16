---
layout: post
title: Codility Lesson 4-4. MaxCounters
tags:
- Codility
---
 Codility Lesson 4-4. MaxCounters 
<br/><br/>
"4-4. MaxCounters - Calculate the values of counters after applying all alternating operations: increase counter by 1; set value of all counters to current maximum."
<br/><br/> 
**This is my answer in C++ (100%)**
vector<int> solution(int N, vector<int> &A) {
    // write your code in C++14 (g++ 6.2.0)
    vector<int> B(N, 0);
    int nCurrMax = 0;
    int nMax = 0;
    
    for (auto &i : A) {
        if (i > N)  nCurrMax = nMax;
        else {
            if (B[i-1] < nCurrMax)  B[i-1] = nCurrMax + 1;
            else B[i-1]++;
            
            if (nMax < B[i-1])  nMax = B[i-1];
        }
    }
    for (auto &j : B) {
        if (j < nCurrMax)   j = nCurrMax;
    }
    return B;
}