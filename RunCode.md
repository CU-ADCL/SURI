---
title: Run The Code 
layout: splash 
permalink: /RunCode/
class: code
---

# Run the Code

Julia package for SDA planning and hypothesis resolution. This package contains algorithms to create and update a sensor tasking plan in order to both perform the task of catalog maintenance and resolve an operator hypothesis over an object of interest.

The code will be updated over the course of the project, so **it is extemely important to [update the code](#Updating) before you start working with the code** to ensure that you have the latest version.

## Getting Started

### 1. Install [Julia](https://julialang.org/)

Download Julia by following the instructions at https://julialang.org/downloads/ .
Installation, updating and testing are performed in [Julia's `pkg>` mode](https://docs.julialang.org/en/v1/stdlib/Pkg/). To enter `pkg>` mode, press `]` in julia. To return to normal julia execution mode from `pkg>` mode, press backspace.

### 2. Clone [SDAPOMDPs.jl](https://github.com/CU-ADCL/SDAPOMDPs.jl)
```bash
git clone https://github.com/CU-ADCL/SDAPOMDPs.jl.git
```

### 3. Activate experiment environment
In the SDAPOMDPs.jl directory execute the following command in the command-line to initialize the project:
```bash
julia init.jl
```

A julia REPL can then be started by simply executing `julia` in the command-line.

The experimental environment should be activated before any experiments are run with the following command being executed in the julia `pkg` mode:
```julia
pkg> activate experiments
```
.


* Currently due to SatelliteDynamics.jl dependency on [SOFA.jl](https://github.com/sisl/SOFA.jl), it only supports Unix systems (MacOS and Linux). In order to use SatelliteDynamics.jl on Windows systems, the Windows Subsystem for Linux ([WSL](https://learn.microsoft.com/en-us/windows/wsl/install)) with a [GCC](https://gcc.gnu.org/) installation is required.

### 4. Running a simulation
```bash
julia --project=experiments experiments/demo.jl
```

The demo.jl file in [SDAPOMDPs.jl](#2-install-sdapomdpsjl) can be used to run MC simulations with n_sim = N simulations (for a single simulation set n_sim=1).  
A quick analysis of the results, stored in the hist DataFrame, can be performed by the `revisedPlan = analyzeHist(bmdp, hist, modelList, dir2save)` function.  
Where `bmdp` is the belief-MDP model, `hist` is the simulation history, `modelList` is a vector of strings describing the different hypothesis models, and `dir2save` is an optional string describing the library to save results and plots.  
The function returns the nominal/initial and the final/revised sensor tasking schedule, and prints the means of the cumulative reward, number of changes to the plan, steps to resolve the hypothesis, and observations to the object of interest taken before making a decision.


### 5. Optional ILP Simulation
For some intuition into how the integer linear program (ILP) solution performs, one may execute

```bash
julia --project=experiments experiments/ilp-plan.jl
```

from the base SDAPOMDPs.jl directory to generate an animation illustrating the sensor tasking strategy of 3 ground-based sensors for a 12-hour period.

## Additional Information/FAQs

### How do I edit Julia source files?

Unlike MATLAB, but like most other programming languages, Julia does not come bundled with an editor. People looking for a MATLAB-like experience may wish to use the [Julia for VS Code](https://www.julia-vscode.org/) IDE. A list of other editors that have Julia integration can be found by scrolling down on the [Julia webpage](julialang.org).

### What are the differences between Julia and MATLAB/Python?

A list of differences can be found [here](https://docs.julialang.org/en/v1/manual/noteworthy-differences/).

### How do I make my Julia code fast?

You can find performance tips [here](https://docs.julialang.org/en/v1/manual/performance-tips/).

### Can I use Python code with Julia?

Python and Julia are capable of interoperating and it may be possible to complete many of the homework assignments using python, however the course staff cannot guarantee support, and python may be too slow in some instances. Python and julia interop is supported by [PythonCall](https://github.com/JuliaPy/PythonCall.jl)




