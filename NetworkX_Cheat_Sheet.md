# NetworkX Cheat Sheet

## networkx.Graph.subgraph

return a SubGraph view

To create a subgraph with its own copy of the edge/node attributes use:

`G.subgraph(nodes).copy()`

For an inplace reduction of a graph to a subgraph you can remove nodes:

`G.remove_nodes_from([n for n in G if n not in set(nodes)])`

## networkx.Graph.edge_subgraph

return the subgraph induced by the specified edges.

To create a full graph version of the subgraph with its own copy of the edge or node attributes.

use:

`G.edge_subgraph(edges).copy()`

