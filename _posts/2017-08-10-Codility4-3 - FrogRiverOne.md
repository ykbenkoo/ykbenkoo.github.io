---
layout: post
title: Codility Lesson 4-3. FrogRiverOne
tags:
- Codility
---
 Codility Lesson 4-3. FrogRiverOne 
<br/><br/>
"4-3. FrogRiverOne - Find the earliest time when a frog can jump to the other side of a river."
<br/><br/> 
**This is my answer in C++ (100%)**
int solution(int X, vector<int> &A) {
    // write your code in C++14 (g++ 6.2.0)
    if (X == 0 && A[0] >= 1)    return -1;
    
    vector<int> B(X, 0);
    int nGoal = 0;
    if ( X <= 1) nGoal = X;
    else {
        nGoal = (X + 1) * (X / 2);
        if (X % 2)  nGoal += (X / 2) + 1;
    }
                
    for (auto i = 0; i < A.size(); ++i)
    {
        if (B[A[i] - 1] == 0) {
            B[A[i] - 1] = A[i];
            nGoal -= A[i];
            //cout << "nGoal : " << nGoal << ", A[" << i << "] : " << A[i] << endl;
            if (nGoal == 0) return i;
        }        
    }
    return -1;
}