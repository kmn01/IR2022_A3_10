# Link Analysis | PageRank, Hubs, Authority


## 1. Unigram Inverted Index

### Preprocessing steps
* Removing irrelevant contents of the file
* Separating NodeIDs using regex
* Finding the edges: from the separated node id list, a set of two consecutive elements represents an edge from the first element to the second element. i.e. [1,2,3,4] has two edges 1->2 and 3->4 storing node ids in from and to list
* Checking for self-loops

### Methodology
Dataset Description: 
Gnutella peer-to-peer network, August 8 2002  
This dataset contains a set of snapshots of the Gnutella peer-to-peer file-sharing network from August 2002. In the graph network, the hosts in the Gnutella network topology are represented by the nodes and the connections between the Gnutella hosts are represented by the edges. The network contains 6301 nodes and 20777 edges.

* Creation of Adjacency Matrix:
> * Storing all the nodes
> * Checking if node id is a set of consecutive whole numbers starting from 0 so they can be used as labels
> * Initializing the matrix with 0s
> * Filling the adjacency matrix list, if adjmat[a][b]=1, this means a->b is an edge

* Creation of Edge List:
> * Adding all nodes to which a node has an edge in a list
> * We do this for all nodes and store the result in a dictionary 

* Local Clustering Coefficient
> * Formula for directed graph:  Nv / (Kv * (Kv - 1))  where V is a vertex, Nv denotes the number of links between neighbours of V and Kv denotes the number of neighbours of V
> * Iterating over each node in the graph, we find the number of neighbours using a modified adjacency matrix that considers all incoming and outgoing edges.
> * Traversing the adjacency matrix by looping over the neighbours of each node, we calculate the number of links between the neighbours of each node.
> * We calculate Local Clustering Coefficient using the formula and the values calculated above.


## 2. PageRank, Hubs and Authority

### Methodology
* Iterating over the list of nodes with outgoing edges 
* Adding edges for each pair to the graph structure using networkx
* Calculating PageRank using networkx.pagerank() function
* Calculating the hub score and authority score using networkx.hits() function

### Comparison of Results from PageRank, Authority Score and Hub Score
* PageRank, Authority Score and Hub Score are measures of the quality of nodes in a network based on the incoming and outgoing links.
* PageRank computes a ranking of nodes in the graph based on the structure of the incoming links, while the HITS algorithm computes the authority score for a node based on the incoming links and the hub score based on outgoing links.
* Good hub pages are defined as pages that point to many authoritative pages for a topic while a good authoritative page is pointed to by many good hubs for that topic.
* Therefore, higher hub score denotes more outgoing links while higher authority score and page rank denote higher incoming links.


## *Contact us:*

* Gitansh: gitansh19241@iiitd.ac.in

* Kirthana: kirthana19053@iiitd.ac.in
