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
<br/>// you can use includes, for example:
<br/>#include <algorithm>
<br/>
<br/>// you can write to stdout for debugging purposes, e.g.
<br/>// cout << "this is a debug message" << endl;
<br/>
<br/>int solution(vector&lt;int&gt; &A) {
<br/>&nbsp; &nbsp;    // write your code in C++14 (g++ 6.2.0)
<br/>&nbsp; &nbsp;    if (A.size() <= 0)      return 1;
<br/>&nbsp; &nbsp;    else if (A.size() == 1 && A[0] == 1)    return 1;
<br/>&nbsp; &nbsp;    
<br/>&nbsp; &nbsp;    vector&lt;int&gt; B = A;
<br/>&nbsp; &nbsp;    sort(B.begin(), B.end());
<br/>&nbsp; &nbsp;    
<br/>&nbsp; &nbsp;    for (auto i = 0; i < B.size(); ++i) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;       if (B[i] != i + 1)      return 0;
<br/>&nbsp; &nbsp;    }
<br/>&nbsp; &nbsp;    return 1;
<br/>}