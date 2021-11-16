---
layout: post
title: SOLID - Liskov Substitution Principle
tags:
- SOLID
---
SOLID - Liskov Substitution Principle
<br/>
<br/>Goal of this principle is to specify that subtypes should be immediately substitutable for their base types
<br/>and expected result should be appeared when I use subtypes instead of base types.
<br/>
<br/>Here is one of samples to break Liskov Substitution Principle.
<br/>
<br/>When we are using subtypes, we cannot get expectation.
<br/>// Objects in a program should be replaceable with instances of their subtypes
<br/>// w/o altering the correctness of the program
<br/>
<br/>#include &lt;iostream&gt;
<br/>
<br/>class Rectangle
<br/>{
<br/>protected:
<br/>&nbsp; &nbsp;  int width, height;
<br/>public:
<br/>&nbsp; &nbsp;  Rectangle(const int width, const int height)
<br/>&nbsp; &nbsp; &nbsp; &nbsp;    : width{width}, height{height} { }
<br/>&nbsp; &nbsp;
<br/>&nbsp; &nbsp;  int get_width() const { return width; }
<br/>&nbsp; &nbsp;  virtual void set_width(const int width) { this->width = width; }
<br/>&nbsp; &nbsp;  int get_height() const { return height; }
<br/>&nbsp; &nbsp;  virtual void set_height(const int height) { this->height = height; }
<br/>
<br/>&nbsp; &nbsp;
<br/>&nbsp; &nbsp;  int area() const { return width * height; }
<br/>};
<br/>&nbsp; &nbsp;
<br/>class Square : public Rectangle
<br/>{
<br/>public:
<br/>&nbsp; &nbsp;  Square(int size): Rectangle(size,size) {}
<br/>&nbsp; &nbsp;  void set_width(const int width) override {
<br/>&nbsp; &nbsp;    this->width = height = width;
<br/>&nbsp; &nbsp;  }
<br/>&nbsp; &nbsp;  void set_height(const int height) override {
<br/>&nbsp; &nbsp;    this->height = width = height;
<br/>&nbsp; &nbsp;  }
<br/>};
<br/>&nbsp; &nbsp;
<br/>struct RectangleFactory
<br/>{
<br/>&nbsp; &nbsp;  static Rectangle create_rectangle(int w, int h);
<br/>&nbsp; &nbsp;  static Rectangle create_square(int size);
<br/>};
<br/>&nbsp; &nbsp;
<br/>void process(Rectangle& r)
<br/>{
<br/>&nbsp; &nbsp;  int w = r.get_width();
<br/>&nbsp; &nbsp;  r.set_height(10);
<br/>&nbsp; &nbsp;
<br/>&nbsp; &nbsp;  std::cout << "expected area = " << (w * 10) 
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     << ", got " << r.area() << std::endl;
<br/>}
<br/>&nbsp; &nbsp;
<br/>int main()
<br/>{
<br/>&nbsp; &nbsp;  Rectangle r{ 5,5 };
<br/>&nbsp; &nbsp;  process(r);
<br/>&nbsp; &nbsp;
<br/>&nbsp; &nbsp;  Square s{ 5 };
<br/>&nbsp; &nbsp;  process(s);
<br/>&nbsp; &nbsp;
<br/>&nbsp; &nbsp;  getchar();
<br/>&nbsp; &nbsp;  return 0;
<br/>}