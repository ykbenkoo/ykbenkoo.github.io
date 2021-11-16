---
layout: post
title: SOLID - Interface Segregation Principle
tags:
- SOLID
---
SOLID - Interface Segregation Principle
<br/>
<br/>The basic idea of interface segregation principle is to get you to not create interfaces
<br/>which are too large which require the implementors to maybe implement too much.
<br/>The core of this principle is to avoid stuffing too much into a single interface 
<br/>and instead if it make sense if you don't want to force declined to implement too much 
<br/>just break up your interface into separate interfaces or just at least make them smaller
<br/>so that whenever a client uses one of these chunks.
<br/>
<br/>#include &lt;vector&gt;
<br/>struct Document;
<br/>
<br/>//struct IMachine
<br/>//{
<br/>//&nbsp; &nbsp;   virtual void print(Document& doc) = 0;
<br/>//&nbsp; &nbsp;   virtual void fax(Document& doc) = 0;
<br/>//&nbsp; &nbsp;   virtual void scan(Document& doc) = 0;
<br/>//};
<br/>//
<br/>//struct MFP : IMachine
<br/>//{
<br/>//&nbsp; &nbsp;   void print(Document& doc) override;
<br/>//&nbsp; &nbsp;   void fax(Document& doc) override;
<br/>//&nbsp; &nbsp;   void scan(Document& doc) override;
<br/>//};
<br/>
<br/>// 1. Recompile
<br/>// 2. Client does not need this
<br/>// 3. Forcing implementors to implement too much
<br/>
<br/>struct IPrinter
<br/>{
<br/>&nbsp; &nbsp;   virtual void print(Document& doc) = 0;
<br/>};
<br/>
<br/>struct IScanner
<br/>{
<br/>&nbsp; &nbsp;   virtual void scan(Document& doc) = 0;
<br/>};
<br/>
<br/>struct Printer : IPrinter
<br/>{
<br/>&nbsp; &nbsp;   void print(Document& doc) override;
<br/>};
<br/>
<br/>struct Scanner : IScanner
<br/>{
<br/>&nbsp; &nbsp;   void scan(Document& doc) override;
<br/>};
<br/>
<br/>struct IMachine: IPrinter, IScanner
<br/>{
<br/>};
<br/>
<br/>struct Machine : IMachine
<br/>{
<br/>&nbsp; &nbsp;   IPrinter& printer;
<br/>&nbsp; &nbsp;   IScanner& scanner;
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   Machine(IPrinter& printer, IScanner& scanner)
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     : printer{printer},
<br/>&nbsp; &nbsp; &nbsp; &nbsp;       scanner{scanner}
<br/>&nbsp; &nbsp;   {
<br/>&nbsp; &nbsp;   }
<br/>&nbsp; &nbsp; 
<br/>&nbsp; &nbsp;   void print(Document& doc) override {
<br/>&nbsp; &nbsp; &nbsp; &nbsp;     printer.print(doc);
<br/>&nbsp; &nbsp;   }
<br/>&nbsp; &nbsp;   void scan(Document& doc) override;
<br/>};
<br/>
<br/>// IPrinter --> Printer
<br/>// everything --> Machine