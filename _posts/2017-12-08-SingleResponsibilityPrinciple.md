---
layout: post
title: SOLID - Single Responsibility Principle
tags:
- SOLID
---
SOLID - Single Responsibility Principle
<br/><br/>
What Single Responsibilty Principle basically state is that a class should have a single reason to change.
<br/><br/>
If you did not separate responsibility, when you want to change some function you have to change all of these methods in many classes.
<br/><br/>
Here is sample code.
<br/>
<br/>#include &lt;iostream&gt;
<br/>#include &lt;fstream&gt;
<br/>#include &lt;string&gt;
<br/>#include &lt;vector&gt;
<br/>#include &lt;boost/lexical_cast.hpp&gt;
<br/>using namespace std;
<br/>
<br/>struct Journal
<br/>{
<br/>&nbsp; &nbsp;   string title;
<br/>&nbsp; &nbsp;   vector&lt;string&gt; entries;
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   explicit Journal(const string& title)
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     : title{title}
<br/>&nbsp; &nbsp;   {
<br/>&nbsp; &nbsp; }
<br/>
<br/>&nbsp; &nbsp;   void add(const string& entry);
<br/>
<br/>&nbsp; &nbsp;   // persistence is a separate concern
<br/>&nbsp; &nbsp;   void save(const string& filename);
<br/>};
<br/>
<br/>void Journal::add(const string& entry)
<br/>{
<br/>&nbsp; &nbsp;   static int count = 1;
<br/>&nbsp; &nbsp; entries.push_backboost::lexical_cast&lt;string&gt;(count++) + ": " + entry);
<br/>}
<br/>
<br/>void Journal::save(const string& filename)
<br/>{
<br/>&nbsp; &nbsp;   ofstream ofs(filename);
<br/>&nbsp; &nbsp;   for (auto& s : entries)
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     ofs << s << endl;
<br/>}
<br/>
<br/>struct PersistenceManager
<br/>{
<br/>&nbsp; &nbsp;   static void save(const Journal& j, const string& filename)
<br/>&nbsp; &nbsp;   {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     ofstream ofs(filename);
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     for (auto& s : j.entries)
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;       ofs << s << endl;
<br/>&nbsp; &nbsp;  }
<br/>};
<br/>
<br/>void main()
<br/>{
<br/>&nbsp; &nbsp;   Journal journal{"Dear Diary"};
<br/>&nbsp; &nbsp;   journal.add("I ate a bug");
<br/>&nbsp; &nbsp;   journal.add("I cried today");
<br/>
<br/>&nbsp; &nbsp;   //journal.save("diary.txt");
<br/>
<br/>&nbsp; &nbsp;   PersistenceManager pm;
<br/>&nbsp; &nbsp;   pm.save(journal, "diary.txt");
<br/>}
<br/>