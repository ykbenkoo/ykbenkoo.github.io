---
layout: post
title: Codility Lesson 5-4. GeomicRangeQuery 
tags:
- Codility
---
 Codility Lesson 5-4. GeomicRangeQuery
<br/><br/>
"1. GenomicRangeQuery - Find the minimal nucleotide from a range of sequence DNA."
<br/>
I cannot find the way to optimize this but I think this code is good way to understand.
After a while, I will optimize this. 
<br/> 
**Now I succeed to be correct this but it is not understandable.
<br/>**This is my answer in C++ (100%)**
<br/>#include &lt;memory.h&gt;
<br/>vector&lt;int&gt; solution(string &S, vector&lt;int&gt; &P, vector&lt;int&gt; &Q) {"
<br/>&nbsp; &nbsp;     // write your code in C++14 (g++ 6.2.0) 
<br/>&nbsp; &nbsp;     vector&lt;int&gt; vResult; 
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;     int (*pTemp)[4] = new int[S.length() + 1][4];
<br/>&nbsp; &nbsp;     memset(pTemp, 0, sizeof(int) * 4 * (S.length() + 1));
<br/>&nbsp; &nbsp;     int nA = 0;
<br/>&nbsp; &nbsp;     int nC = 0;
<br/>&nbsp; &nbsp;     int nG = 0;
<br/>&nbsp; &nbsp;     int nT = 0;
<br/>&nbsp; &nbsp;     for (auto i = 1; i < S.length() + 1; ++i) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;          switch (S[i-1]) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;               case 'A': ++nA; break;
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;               case 'C': ++nC; break;
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;               case 'G': ++nG; break;
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;               case 'T': ++nT; break;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;          }
<br/>&nbsp; &nbsp; &nbsp; &nbsp;          pTemp[i][0] = nA;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;          pTemp[i][1] = nC;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;          pTemp[i][2] = nG;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;          pTemp[i][3] = nT;
<br/>&nbsp; &nbsp;}
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp;     int nToIndex =  0;
<br/>&nbsp; &nbsp;     int nFromIndex = 0;
<br/>&nbsp; &nbsp;     for (auto j = 0; j < P.size(); ++j) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;          nToIndex = Q[j] + 1;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;          nFromIndex = P[j] + 1;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;          if (nFromIndex != 0) nFromIndex--;  
<br/>&nbsp; &nbsp; &nbsp; &nbsp;          if (pTemp[nToIndex][0] - pTemp[nFromIndex][0] > 0) vResult.push_back(1);
<br/>&nbsp; &nbsp; &nbsp; &nbsp;          else if (pTemp[nToIndex][1] - pTemp[nFromIndex][1] > 0) vResult.push_back(2);
<br/>&nbsp; &nbsp; &nbsp; &nbsp;          else if (pTemp[nToIndex][2] - pTemp[nFromIndex][2] > 0) vResult.push_back(3);
<br/>&nbsp; &nbsp; &nbsp; &nbsp;          else vResult.push_back(4);            
<br/>&nbsp; &nbsp; &nbsp; &nbsp;      } 
<br/>&nbsp; &nbsp;     delete []pTemp;
<br/>&nbsp; &nbsp;     return vResult; 
<br/>}
<br/>
<br/>
**This was my answer in C++ (62%) because of optimization.**
<br/>vector<int> solution(string &S, vector<int> &P, vector<int> &Q) {
<br/>&nbsp; &nbsp;    // write your code in C++14 (g++ 6.2.0)
<br/>&nbsp; &nbsp;    vector<int> vResult;
<br/>&nbsp; &nbsp;    vector<int> vTemp;
<br/>&nbsp; &nbsp;    for (int i = 0; i < S.size(); ++i) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;        if (S[i] == 'A')    vTemp.push_back(1);
<br/>&nbsp; &nbsp; &nbsp; &nbsp;        else if (S[i] == 'C')    vTemp.push_back(2);
<br/>&nbsp; &nbsp; &nbsp; &nbsp;        else if (S[i] == 'G')    vTemp.push_back(3);
<br/>&nbsp; &nbsp; &nbsp; &nbsp;        else if (S[i] == 'T')    vTemp.push_back(4);
<br/>&nbsp; &nbsp;    }
<br/>&nbsp; &nbsp;    int nMin = 5;    
<br/>&nbsp; &nbsp;    int nTemp = 5;
<br/>&nbsp; &nbsp;    for (int i = 0; i < P.size(); ++i) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;        for (int j = P[i]; j <= Q[i]; ++j) {
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;            nTemp = vTemp[j];
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;            if (nMin > nTemp)   nMin = nTemp;   
<br/>&nbsp; &nbsp; &nbsp; &nbsp;       }
<br/>&nbsp; &nbsp; &nbsp; &nbsp;        vResult.push_back(nMin);
<br/>&nbsp; &nbsp; &nbsp; &nbsp;        nTemp = 5;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;        nMin = 5;
<br/>&nbsp; &nbsp;    }
<br/>&nbsp; &nbsp;    return vResult;
<br/>}   