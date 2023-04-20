# EHFMCP_Instances
Repository of instances for the Environmental Heterogeneous Fleet Milk Collection Problem (EHFMCP).

The problem is a variation of the well-known Vehicle Routing Problem (VRP) in which a set of vehicles leaves a dairy processing plant, travels through a set of dairy farms collecting the production, and then returns to the processing plant.

The aim is to determine the routes that minimize $CO_2$ emissions considering that the carrying capacity of the vehicles should not be exceeded and that the entire production of all the farms should be collected.

The polluting emission rate ($\alpha_k$) of the type $k$ vehicle is calculated as:

$$\displaystyle \alpha_k = \frac{E^f_k-E^0_k}{Q_k}$$

Where $E^f_k$ and $E^0_k$ are the emission levels of the type $k$ vehicle with full load and empty respectively measured in $CO_2$ kilograms per kilometer traveled, and $Q_k$ is the load capacity of the vehicle $k$ in litres.

The objective function of the problem is:

$$\displaystyle Min \sum_{i=0}^{n} \sum_{j=0}^{n} \sum_{k=1}^{m} \left ( E^0_k  x_{ijk}  + \alpha_k y_{ijk} \right) d_{ij}$$

Where $x_{ijk}$ is a binary variable that determines whether vehicle $k$ makes the journey between two nodes ($ij$), and $y_{ijk}$ is the variable that determines the amount of milk that vehicle $k$ transports between two nodes ($ij$). $d_{ij}$ is the distance in kilometers between two nodes ($ij$). The nodes are the farms and the processing plant. Additionally, it should be considered that all dairy farms must be served one time by one vehicle. 

Two versions of the problem are considered:
* The Heterogeneous Vehicle Routing Problem (HVRP) with a fixed quantity of each type of vehicle ($b_k$).
* The Fleet-Size and Mix (FSM) that aims to determine the fleet and the routes.

The Instance Data folder contains the 36 detailed instances. There are four versions combining two factors, those with the central (CEN) or corner (COR) processing plant, and those with uniformly distributed farms (NOCLUS) and those with clustered farms (CLUS). There are three instances of each combination for 20, 35, and 50 farms.

The details of the instances are:
* There are three types of vehicles ($V1$, $V2$, and $V3$)
* Load is the capacity of each vehicle in liters ($Q_k$)
* Num_v is the number of available vehicles ($b_k$)
* Ef and Eo are $E^f_k$ and $E^0_k$ respectively
* Node are the nodes of the problem, $P$ for the processing plant and $F1$, $F2$, ... for the farms
* coord_x and coord_y are the Cartesian coordinates of each node
* prod is the production of milk of each farm ($p$) 

For information about the problem please contact Luis Francisco López Castro (luis.lopez3@unisabana.edu.co)


