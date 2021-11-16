---
layout: post
title: Codility Lesson 5-2. PassingCars 
tags:
- Codility
---
 Codility Lesson 5-2. PassingCars 
<br/><br/>
"5-2. PassingCars - Count the number of passing cars on the road."
<br/><br/> 
**This is my answer in C++ (100%)**
int solution(vector<int> &A) {
    // write your code in C++14 (g++ 6.2.0)    
    /****** This code was time-limited.
    for (auto iter = A.begin(); iter != A.end(); ++iter) {
        if (*iter == 0) {            
            nSum += count_if(iter, A.end(), [](int & n){ return n == 1; });            
        }
    }
    *********/

    vector<int> B;
    int nSum = 0;
    int nASize = A.size();
    
    if (nASize <= 1) return 0;
    for (auto i = 0; i < nASize; ++i)
    {
        if (A[i] == 0) {
            B.push_back(i);
        }
    }
    int nBSize = B.size();
    if (nBSize <= 0) {
        return 0;
    }
    else if (nBSize == 1){
        if (B[0] < nASize)  return nASize - B[0] - 1;
    }
    else {
        for (auto j = 0; j < nBSize - 1; ++j)
        {
            nSum += (B[j+1] - B[j] - 1) * (j + 1);
            if (j == nBSize - 2)  {
                nSum += (nASize - (B[j+1] + 1)) * nBSize; 
            }
        }        
    }
    if (nSum < 0 || nSum > 1000000000)  return -1;
    return nSum;
}