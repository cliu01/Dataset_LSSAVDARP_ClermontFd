# Dataset_LSSAVDARP_ClermontFd

In this repository, we share a self-generated data set used to simulate the requests in a prospective large-scale shared autonomous vehicle (SAV) dial-a-ride (DAR) transportation system in the city of clermont-ferrand and its peri-areas. Following is a short description of our dataset.


##  Graph
We select the network of the city of Clermont-Ferrand, France, and its suburbs. 
The selected transit network contains 13,839 nodes and 31,357 arcs. Each node is associated with a type: (W: working place, R: residential place, U: unclassified). Among all the nodes, we keep 1,460 to be pickup/drop-off locations. Statistics of these pickup/drop-off locations are given in the table below.

| Node Type | Column 2 | Column 3 | Column 4 |
|----------|----------|----------|----------|
|   Count  |   574   |   788   |   98    |
|  Proportion |   39.3%   |   54%   |   6.7%    |

In the folder `Network/`, we can typically find the following files:
  - `nodes.txt`:  all the nodes in the network
  - `distances.txt`: all the arcs in the network
  - `depot.txt`: the depot of the SAVs
  - `into/reduced_location.txt`: the nodes selected to be pickup/drop-off locations under each node type.


## Requests
We consider 5 different sizes of the request set: 10k, 50k, 100k, 200k, 300k. 
For each problem size, we generate 5 different instances: I0, I1, I2, I3, I4, I5
Under each instance, we have 5 variations.
For example, in the folder `10k/`, we can find for instance I0:  
- `I0.txt` : the standard static instance
- `I0_single.txt`: the static instance, same as `I0.txt`, but the load of all requests is fixed at 1
- `I0_dynamic_50.txt`, `I0_dynamic_70.txt`, `I0_dynamic_100.txt`: the dynamic instances generated based on `I0.txt`, but each request is associated with a submission time. The figures 50, 70 and 100 indicates the share of dynamic requests among all the requests.

For the record, in these files, each row is a request of the format (origin_node, destination_node, load, earliest pickup time (in centi-second), submission time (in centi-second)).

