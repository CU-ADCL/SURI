
**Demo Results**

To test the code we simulated 1600 seconds of trajectory, with a time step of 20 seconds. In this scenario, there are 5 SO's, where one of them is the object of interest (OOI).   
The OOI moves in an unperturb nominal Keplerian orbit. However, an operator decides to investigate two competing hypothesis (in addition to the nominal): (i) the OOI deployed a set of small solar panels, which correspond to an area drag of 1, and (ii) the OOI deployed a larger set of solar panels, which corresponds to area drag of 5.  
In each decision point, the planning algorithm decides wheter to proceed with the nominal tasking plan, or change it to observe the OOI, with the goal of differentiating between the 3 hypotheses, and eventually deciding on the most probable one.  
The graph below shows the probability values for each hypothesis vs. time. As can be seen from the graph, it taks about 30 time steps to start differentiating between hypotheses, and the algorithm converges to the correct one with about $$75\%$$ confidence.


<img src="assets/images/histogram.svg" alt="Image" style="max-width: auto; height: auto;">
