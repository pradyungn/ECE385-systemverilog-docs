---
title: modules
type: docs
weight: 5
---

# Modules

As we started to discuss in the main SV page, modules are how SystemVerilog fundamentally organizes and abstracts hardware designs. Here we'll go over an example of how a simple module is instantiated, how to manage multiple modules in a project, and using module parameters.

## Creating Your First Module

For our first module, let's keep it simple - we will make a simple one-bit inverter.

```systemverilog
module inverter(input A, output B);
    assign B = ~A;
endmodule
```

That's a lot of  new syntax! Let's break it down. There's two main things to pay attention to here.

### The Module Header

This is how we tell SystemVerilog that we'll be making a new module. A module is generally written with the following format:

```systemverilog
module {{NAME}}({{INTERFACE});
	// logic
endmodule
```

Where your interface is a comma-separated list of ports in your module. Your ports for a module can be of three types, where the descriptor is from the perspective of the module:

* `input`
* `output`
* `inout`: both and input and output. You won't really use this in your own code for this class, but you'll see it in some auto-generated modules that we use later on in the course.

This syntax is how any and all modules are declared in SystemVerilog.

## Module Parameters

>  Note: This  section of the document is intended for people who are already comfortable making basic modules in SystemVerilog. We recommend revisiting this section after you've gotten a decent grasp on how to write your own modules.