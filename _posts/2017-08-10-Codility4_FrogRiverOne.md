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
<br/>int solution(int X, vector&lt;int&gt; &A) {
<br/>&nbsp; &nbsp;    // write your code in C++14 (g++ 6.2.0)
<br/>&nbsp; &nbsp;    if (X == 0 && A[0] >= 1)    return -1;
<br/>&nbsp; &nbsp;    
<br/>&nbsp; &nbsp;    vector&lt;int&gt; B(X, 0);
<br/>&nbsp; &nbsp;    int nGoal = 0;
<br/>&nbsp; &nbsp;    if ( X <= 1) nGoal = X;
<br/>&nbsp; &nbsp;    else {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         nGoal = (X + 1) * (X / 2);
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (X % 2)  nGoal += (X / 2) + 1;
<br/>&nbsp; &nbsp;    }
<br/>&nbsp; &nbsp;                
<br/>&nbsp; &nbsp;    for (auto i = 0; i < A.size(); ++i)
<br/>&nbsp; &nbsp;    {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (B[A[i] - 1] == 0) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp;             B[A[i] - 1] = A[i];
<br/>&nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp;             nGoal -= A[i];
<br/>&nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp;             //cout << "nGoal : " << nGoal << ", A[" << i << "] : " << A[i] << endl;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp;             if (nGoal == 0) return i;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;        }        
<br/>&nbsp; &nbsp;    }
<br/>&nbsp; &nbsp;    return -1;
<br/>}