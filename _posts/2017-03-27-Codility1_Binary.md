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
<br/>int solution(int N) {
<br/>&nbsp; &nbsp;     // write your code in C++14 (g++ 6.2.0)
<br/>&nbsp; &nbsp;     int nOneCount = 0;
<br/>&nbsp; &nbsp;     int nCount = 0;
<br/>&nbsp; &nbsp;     int nMaxCount = 0;
<br/>&nbsp; &nbsp;     while (N) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;         if (N % 2) { 
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;          if (nMaxCount < nCount) nMaxCount = nCount;
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;          nCount = 0;
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;         nOneCount++;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;        }
<br/>&nbsp; &nbsp; &nbsp; &nbsp;        else if (nOneCount) nCount++;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;        N = N / 2;
<br/>&nbsp; &nbsp;    }
<br/>&nbsp; &nbsp;    return nMaxCount;
<br/>}
