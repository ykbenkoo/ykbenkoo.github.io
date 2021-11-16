---
layout: post
title: SOLID - Open closed Principle
tags:
- SOLID
---
SOLID - Open closed Principle
<br/>
<br/>Open-Closed Principle basically states that your system should be open to extensions 
<br/>so you should be able to extend system by inheritance but closed for modification 
<br/>Just to reiterate what I've already started the goal of the open closed principle is 
<br/>to avoid having to jump into code that you've already written. 
<br/>Open for extension meaning that you can always make and use specification by extending and inheriting effectively
<br/>but closed for modification which means that in the context of the specification pattern. 
<br/>you would never require yourself to go back into the filter interface or the let's say the specification. 
<br/>It wouldn't have to change those you would extend by them by inheritance and then 
<br/>you would create maybe these combinators like we have and specification you can make or specification and so on. 
<br/><br/>Here is sample code.
<br/>
<br/>// open closed principle
<br/>
<br/>// open for extension, closed for modification
<br/>
<br/>#include &lt;string&gt;
<br/>#include &lt;vector&gt;
<br/>#include &lt;iostream&gt;
<br/>using namespace std;
<br/>
<br/>enum class Color { Red, Green, Blue };
<br/>enum class Size {Small, Medium, Large };
<br/>
<br/>struct Product
<br/>{
<br/>&nbsp; &nbsp;   string name;
<br/>&nbsp; &nbsp;   Color color;
<br/>&nbsp; &nbsp;   Size size;
<br/>};
<br/>
<br/>struct ProductFilter
<br/>{
<br/>&nbsp; &nbsp;   typedef vector&lt;Product*&gt; Items;
<br/>
<br/>&nbsp; &nbsp;   static Items by_color(Items items, Color color);
<br/>
<br/>&nbsp; &nbsp;   static Items by_size(Items items, Size size)
<br/>&nbsp; &nbsp;   {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     Items result;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     for (auto& i : items)
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;       if (i->size == size)
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;         result.push_back(i);
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     return result;
<br/>&nbsp; &nbsp;   }
<br/>
<br/>&nbsp; &nbsp;   // size and color
<br/>&nbsp; &nbsp;   static Items by_color_and_size(Items items, Size size, Color color);
<br/>
<br/>&nbsp; &nbsp;   // violated OCP b/c we had to jump in and change the underlying object
<br/>&nbsp; &nbsp;   // stable objects are easier to maintain
<br/>};
<br/>
<br/>ProductFilter::Items ProductFilter::by_color(Items items, Color color)
<br/>{
<br/>&nbsp; &nbsp;   Items result;
<br/>&nbsp; &nbsp;   for (auto& i : items)
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     if (i->color == color)
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;       result.push_back(i);
<br/>&nbsp; &nbsp;   return result;
<br/>}
<br/>
<br/>ProductFilter::Items ProductFilter::by_color_and_size(Items items, Size size, Color color)
<br/>{
<br/>&nbsp; &nbsp;   Items result;
<br/>&nbsp; &nbsp;   for (auto& i : items)
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     if (i->size == size && i->color == color)
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;       result.push_back(i);
<br/>&nbsp; &nbsp;   return result;
<br/>}
<br/>
<br/>template <typename T> struct AndSpecification;
<br/>
<br/>template <typename T> struct Specification
<br/>{
<br/>&nbsp; &nbsp;   virtual bool is_satisfied(T* item) = 0;
<br/>
<br/>&nbsp; &nbsp;   AndSpecification<T> operator &&(Specification& other)
<br/>&nbsp; &nbsp;   {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     return AndSpecification<T>(*this, other);
<br/>&nbsp; &nbsp;   }
<br/>};
<br/>
<br/>
<br/>
<br/>template <typename T> struct Filter
<br/>{
<br/>&nbsp; &nbsp;   virtual vector&lt;T*&gt; filter(vector&lt;T*&gt; items, Specification<T>& spec) = 0;
<br/>};
<br/>
<br/>struct BetterFilter : Filter<Product>
<br/>{
<br/>&nbsp; &nbsp;   vector&lt;Product*&gt; filter(vector&lt;Product*&gt; items, Specification<Product>& spec) override
<br/>&nbsp; &nbsp;   {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     vector&lt;Product*&gt; result;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     for (auto& p : items)
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;       if (spec.is_satisfied(p))
<br/>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;         result.push_back(p);
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     return result;
<br/>&nbsp; &nbsp;   }
<br/>};
<br/>
<br/>struct ColorSpecification : Specification<Product>
<br/>{
<br/>&nbsp; &nbsp;   Color color;
<br/>
<br/>&nbsp; &nbsp;   explicit ColorSpecification(const Color color)
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     : color{color}
<br/>&nbsp; &nbsp;   {
<br/>&nbsp; &nbsp;   }
<br/>  
<br/>&nbsp; &nbsp;   bool is_satisfied(Product* item) override {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     return item->color == color;
<br/>&nbsp; &nbsp;   }
<br/>};
<br/>
<br/>struct SizeSpecification : Specification<Product>
<br/>{
<br/>&nbsp; &nbsp;   Size size;
<br/>
<br/>&nbsp; &nbsp;   explicit SizeSpecification(const Size size)
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     : size{ size }
<br/>&nbsp; &nbsp;   {
<br/>&nbsp; &nbsp;   }
<br/>
<br/>
<br/>&nbsp; &nbsp;   bool is_satisfied(Product* item) override {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;      return item->size == size;
<br/>&nbsp; &nbsp;   }
<br/>};
<br/>
<br/>&nbsp; &nbsp; template <typename T> struct AndSpecification : Specification<T>
<br/>&nbsp; &nbsp; {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;   Specification<T>& first;
<br/>&nbsp; &nbsp; &nbsp; &nbsp;   Specification<T>& second;
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   AndSpecification(Specification<T>& first, Specification<T>& second)
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     : first{first}, second{second}
<br/>&nbsp; &nbsp;   {
<br/>&nbsp; &nbsp;   }
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   bool is_satisfied(T* item) override
<br/>&nbsp; &nbsp;   {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     return first.is_satisfied(item) && second.is_satisfied(item);
<br/>&nbsp; &nbsp;   }
<br/>};
<br/> 
<br/>int main()
<br/>{
<br/>&nbsp; &nbsp;   Product apple{ "Apple", Color::Green, Size::Small };
<br/>&nbsp; &nbsp;   Product tree{ "Tree", Color::Green, Size::Large };
<br/>&nbsp; &nbsp;   Product house{ "House", Color::Blue, Size::Large };
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   vector&lt;Product*&gt; all{ &apple, &tree, &house };
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   BetterFilter bf;
<br/>&nbsp; &nbsp;   ColorSpecification green(Color::Green);
<br/>&nbsp; &nbsp;   
<br/>&nbsp; &nbsp;   auto green_things = bf.filter(all, green);
<br/>&nbsp; &nbsp;   for (auto& x : green_things)
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     cout << x->name << " is green" << endl;
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   SizeSpecification big(Size::Large);
<br/>&nbsp; &nbsp;   //AndSpecification<Product> green_and_big{ big, green };
<br/>&nbsp; &nbsp;   auto green_and_big = 
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     ColorSpecification(Color::Green)
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     && SizeSpecification(Size::Large);
<br/>&nbsp; &nbsp;     
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   auto big_green_things = bf.filter(all, green_and_big);
<br/>&nbsp; &nbsp;   for (auto& x : big_green_things)
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     cout << x->name << " is big and green" << endl;
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   getchar();
<br/>&nbsp; &nbsp;   return 0;
<br/>}<br/>