---
title: Run The Code 
layout: splash 
permalink: /RunCode/
class: code
---

# Run the Code

Julia package for ... . This package contains ... .

The code will be updated over the course of the project, so **it is extemely important to [update the code](#Updating) before you start working with the code** to ensure that you have the latest version.

## Getting Started

### 1. Install [Julia](https://julialang.org/)

Download Julia by following the instructions at https://julialang.org/downloads/ .

### 2. Install SDAPOMDPs.jl
Installation, updating and testing are performed in [Julia's `pkg>` mode](https://docs.julialang.org/en/v1/stdlib/Pkg/). To enter `pkg>` mode, press `]` in julia. To return to normal julia execution mode from `pkg>` mode, press backspace.

```
pkg> add https://github.com/WhiffleFish/SDAPOMDPs.jl.git
```

### Updating

Always use the latest version. To get the latest version, run
```
pkg> update
```


## Additional Information/FAQs

### How do I edit Julia source files?

Unlike MATLAB, but like most other programming languages, Julia does not come bundled with an editor. People looking for a MATLAB-like experience may wish to use the [Julia for VS Code](https://www.julia-vscode.org/) IDE. A list of other editors that have Julia integration can be found by scrolling down on the [Julia webpage](julialang.org).

### What are the differences between Julia and MATLAB/Python?

A list of differences can be found [here](https://docs.julialang.org/en/v1/manual/noteworthy-differences/).

### How do I make my Julia code fast?

You can find performance tips [here](https://docs.julialang.org/en/v1/manual/performance-tips/).

### Can I use Python code with Julia?

Python and Julia are capable of interoperating and it may be possible to complete many of the homework assignments using python, however the course staff cannot guarantee support, and python may be too slow in some instances. Python and julia interop is supported by [PythonCall](https://github.com/JuliaPy/PythonCall.jl)




