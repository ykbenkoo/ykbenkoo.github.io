---
layout: post
title: SOLID - Dependency Inversion Principle
tags:
- SOLID
---
SOLID - Dependency Inversion Principle
<br/>Dependency Inversion Principle has two different Idea
<br/>- High-level modules should not depend on low-level modules.
<br/> Both Should depend on abstractions.
<br/>- Abstractions should not depend on details
<br/> Details should depend on abstractions.
<br/> 
<br/> Here is sample code to fix code which is related to Dependency Inversion Principle.
<br/>
<br/>#include &lt;iostream&gt;
<br/>#include &lt;string&gt;
<br/>#include &lt;vector&gt;
<br/>#include &lt;tuple&gt;
<br/>using namespace std;
<br/>
<br/>// A. High-level modules should not depend on low-level modules.
<br/>//    Both should depend on abstractions.
<br/>// B. Abstractions should not depend on details. 
<br/>//    Details should depend on abstractions.
<br/>
<br/>enum class Relationship
<br/>{
<br/>&nbsp;  parent,
<br/>&nbsp;  child,
<br/>&nbsp;  sibling
<br/>};
<br/>
<br/>struct Person
<br/>{
<br/>&nbsp;  string name;
<br/>};
<br/>
<br/>struct RelationshipBrowser
<br/>{
<br/>&nbsp;  virtual vector&lt;Person&gt; find_all_children_of(const string& name) = 0;
<br/>};
<br/>
<br/>struct Relationships : RelationshipBrowser // low-level
<br/>{
<br/>&nbsp; &nbsp;   vector<tuple&lt;Person, Relationship, Person&gt;> relations;
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   void add_parent_and_child(const Person& parent, const Person& child)
<br/>&nbsp; &nbsp;   {
<br/>&nbsp; &nbsp;     relations.push_back({parent, Relationship::parent, child});
<br/>&nbsp; &nbsp;     relations.push_back({child, Relationship::child, parent});
<br/>&nbsp; &nbsp;   }
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   vector&lt;Person&gt; find_all_children_of(const string &name) override
<br/>&nbsp; &nbsp;   {
<br/>&nbsp; &nbsp;     vector&lt;Person&gt; result;
<br/>&nbsp; &nbsp;     for (auto&& [first, rel, second] : relations)
<br/>&nbsp; &nbsp;     {
<br/>&nbsp; &nbsp;       if (first.name == name && rel == Relationship::parent)
<br/>&nbsp; &nbsp;       {
<br/>&nbsp; &nbsp;         result.push_back(second);
<br/>&nbsp; &nbsp;       }
<br/>&nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;     return result;
<br/>&nbsp; &nbsp;   }
<br/>};
<br/>&nbsp; &nbsp; 
<br/>struct Research // high-level
<br/>{
<br/>&nbsp; &nbsp;   Research(RelationshipBrowser& browser)
<br/>&nbsp; &nbsp;   {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     for (auto& child : browser.find_all_children_of("John"))
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     {
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;       cout << "John has a child called " << child.name << endl;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     }
<br/>&nbsp; &nbsp;   }
<br/>&nbsp; &nbsp; //  Research(const Relationships& relationships)
<br/>&nbsp; &nbsp; //  {
<br/>&nbsp; &nbsp; // &nbsp; &nbsp;    auto& relations = relationships.relations;
<br/>&nbsp; &nbsp; // &nbsp; &nbsp;    for (auto&& [first, rel, second] : relations)
<br/>&nbsp; &nbsp; // &nbsp; &nbsp;    {
<br/>&nbsp; &nbsp; // &nbsp; &nbsp; &nbsp; &nbsp;      if (first.name == "John" && rel == Relationship::parent)
<br/>&nbsp; &nbsp; // &nbsp; &nbsp; &nbsp; &nbsp;      {
<br/>&nbsp; &nbsp; // &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;        cout << "John has a child called " << second.name << endl;
<br/>&nbsp; &nbsp; // &nbsp; &nbsp; &nbsp; &nbsp;      }
<br/>&nbsp; &nbsp; // &nbsp; &nbsp;    }
<br/>&nbsp; &nbsp; //  }
<br/>};
<br/>&nbsp; &nbsp; 
<br/>int main()
<br/>{
<br/>&nbsp; &nbsp;   Person parent{"John"};
<br/>&nbsp; &nbsp;   Person child1{"Chris"};
<br/>&nbsp; &nbsp;   Person child2{"Matt"};
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   Relationships relationships;
<br/>&nbsp; &nbsp;   relationships.add_parent_and_child(parent, child1);
<br/>&nbsp; &nbsp;   relationships.add_parent_and_child(parent, child2);
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   Research _(relationships);
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   return 0;
<br/>}