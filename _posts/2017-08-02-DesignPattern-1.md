---
layout: post
title: DesignPattern - 1. What is MVC Pattern?
tags:
- GoF's Design Pattern.
---
<b>Design Pattern using MVC</b>
<br/><br/>
There are three objects in MVC. 
<br/>
First is Model(Application object),
<br/>
Second is View(How to display model)
<br/>
Third is Controller(How to react from user interface)
<br/>
So.. How to make MVC?
<br/>
To begin with, making subscribe/notify protocol between View and model because it can remove dependency.
<br/>
It enables object not to need to know the change of other object.
<br/>
This patern is generally called Supervisor Pattern.
<br/>
Also, MVC is able to be piled up view such as control pannel can involve a various type of buttons
<br/>
and it uses controller to process user`s action without the change of visual presentation by changing Controller interface.
<br/>
View and Controller relationship is one of Strategy Pattern's examples.
<br/>
the main pattern of using in MVC is Supervisor, Composite and Strategy Pattern.
<br/>

