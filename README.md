# Minimum-Cost-Flow
Minimum Cost Flow: In the case study from Guéret et al, (1999), the Minimum Cost Flow Problem was solved to minimise the company’s costs when transferring the required number of cars to different collection points along all arcs of the network, subject to satisfy the demand of each point. The decisions to be made are whether or not each source i will be able to supply destination j. The input parameters to be considered are the following: unit transportation charge, fixed price transportation, and demand at destination j.


"A small car rental company has a fleet of 94 vehicles distributed among its 10 agencies. The location of
every agency is given by its geographical coordinates X and Y in a grid based on kilometers. We assume
that the road distance between agencies is approximately 1.3 times the Euclidean distance (as the crow
flies). The following table indicates the coordinates of all agencies, the number of cars required the next
morning, and the stock of cars in the evening preceding this day.
Table 10.1: Description of the vehical rental agencies
Agency         1    2     3    4    5    6    7    8    9    10
X coordinate   0    20   18   30   35   33    5    5   11     2
Y coordinate   0    20   10   12    0   25   27   10    0    15
Required cars  10    6    8   11    9    7   15    7    9    12
Cars present   8    13    4    8   12    2   14   11   15     7
Supposing the cost for transporting a car is BC 0.50 per km, determine the movements of cars that allow the
company to re-establish the required numbers of cars at all agencies, minimizing the total cost incurred
for transport."



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
