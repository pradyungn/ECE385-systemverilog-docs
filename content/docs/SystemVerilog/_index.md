---
title: SystemVerilog
type: docs
weight: 20
bookCollapseSection: true
---

# SystemVerilog Docs

This section of documentation (and its sub-articles) detail how to use the SystemVerilog language to describe hardware designs. While most of the content in this section is directly paralleled by the content covered in lecture, there are some additional features of SV covered that _are not necessary to get through ECE385_, but are good to know! They can certainly be used in the course to make your HDL more concise.

The rest of this page will, at a high level, introduce you to the SystemVerilog language. The other subpages visible in the left-hand menu will detail specific operators or features of the SystemVerilog language - we've done our best to organize these features in the order that you'll need them in class!

## What is SystemVerilog?

In this class, we do all of our labs in SystemVerilog. SystemVerilog is a popular **HDL**, which stands for "Hardware Description Language".  These languages are essentially instructions that describe how to make a piece of hardware that you are designing. You can almost think of it like a blueprint or a CAD file - but instead of telling a manufacturer what the dimensions and materials for different parts should be and how they piece together, you communicate these design parameters to a ***synthesizer***. The synthesizer is a complex piece of software that understands how to interpret the HDL that you write and will generate a piece of pseudo-hardware.  Unless you're really interested in logic synthesis, don't worry too much about how it does this - just understand that the synthesizer is *translating your hardware description*.

Along a similar vein, a common misconception that students in this class make is that SystemVerilog is a programming language. They come out of 220, see the same old `if` and `case` statements, and immediately conflate the two. However, it is important to understand that *fundamentally*, ***the SystemVerilog you write will never be compiled and ran as code***. While instructions in programming languages like C and Python are executed one at a time, SystemVerilog is parsed all at once - this tends to create a bit of confusion for the more CS-minded students taking this class. Some common no-can-dos that we see include implicit variable assignments, logical `for` loops, and any kind of `while` loop.  Things that tend to be very elementary "fair game" in traditional programming languages. As a result, we encourage you to stick by the following rule of thumb:

> If you see yourself using CS terminology to describe the hardware you are making - like "using a for loop", for example - you are probably using SystemVerilog wrong. For most of this class, the hardware litany that you've learned in ECE 120 should be sufficient to describe the designs that you are personally responsible for.

The biggest difference you'll see between the designs you were making in 120 and this class will be the sheer size and complexity of the design - however, the fundamental logical terms we use (registers, muxes, FSMs, etc.) don't change much.

## How Do I "Use" Hardware in SV?

Hardware in SystemVerilog is fundamentally described as different ***modules***. You can think of a module as a function in C - it has its own set of inputs and outputs, and the other logic interacting with it doesn't need to know what exactly the function/module is doing internally. Just what the expected behavior is! Function calls in C are like  module ***instantiations*** in SV.

Modules are an extremely powerful abstraction in SystemVerilog. Like C functions, they allow for easy integration and repetition of common functionality in hardware. However while multiple function calls in C will execute the same code multiple times sequentially, multiple instantiations in SV will create multiple copies of the same hardware. This is useful when you need to perform the same operation to multiple signals at the same time.  But the greater benefit of modules is abstraction - you can separate individual pieces of logic to make your HDL more readable, easier to debug at a granular level, and more reusable overall. Just be careful not to overdo it - there is such a thing as having too many modules. 

As a designer, there is going to be a module in your HDL that meets your larger goal - this could be as simple as inverting a bit, or as complex as a CPU (shout-out to ECE 411). This module, capable of the overarching functionality you are working towards, is called a **Top-Level Module**. If you want to continue reading about how we create and implement modules in SV, go [here](./modules).
