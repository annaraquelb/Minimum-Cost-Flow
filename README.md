# Minimum-Cost-Flow
Minimum Cost Flow: In the case study from Guéret et al, (1999), the Minimum Cost Flow Problem was solved to minimise the company’s costs when transferring the required number of cars to different collection points along all arcs of the network, subject to satisfy the demand of each point. The decisions to be made are whether or not each source i will be able to supply destination j. The input parameters to be considered are the following: unit transportation charge, fixed price transportation, and demand at destination j.

Analysis of test instance and optimisation results 

This problem was not only solved, but it was also enlarged by adding new sets of constraints.

After defining the two classes and different sources and sinks attributes, the code defines the function for calculating the distance between sources and sinks, transportation unitary cost (cost per km), as well as the fixed cost (total daily salary of drivers). Afterwards,  generic expression used to calculate cost prices from source to sinks are defined:

These previous passages were fundamental to derive our objective function, which is as it follows:
prob += two_one*x21 + two_three*x23 + two_four*x24 + two_six*x26 + two_seven*x27 + two_ten*x210 + \
five_one*x51 + five_three*x53 + five_four*x54 + five_six*x56 + five_seven*x57 + five_ten*x510 + \
eight_one*x81 + eight_three*x83 + eight_four*x84 + eight_six*x86 + eight_seven*x87 + eight_ten*x810 + \
nine_one*x91 + nine_three*x93 + nine_four*x94 + nine_six*x96 + nine_seven*x97 + nine_ten*x910

This function intends to minimise the cost of transportation while calculating the distance from each supplier to each sink. Moreover, two more constraints are added to provide optimised solutions to each car agency and each supplier, depending on their demand and capacity:

Constraint 1: Number of cars supplied from provider to collection point (xij) should be equal (==) to the number of car providers are able to supply (ci):


The a in the above results stands for the arch that connect agency i to agency j.
