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
**This is my answer in C++ (100%)**
int solution(int X, int Y, int D) {
    // write your code in C++14 (g++ 6.2.0)
    return (((Y-X) / D) + (((Y-X) % D) >= 1));
}