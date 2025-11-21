
# LAB3- find the shortest path even with grafh with negative archs

I tried several solutions to solve the problem and I ended up concluding that Bellman–Ford is the best choice in terms of correctness on graphs with negative weights and acceptable efficiency on the sizes I tested. I implemented the well‑known algorithm (after researching references online) and compared my results with NetworkX to validate the outcomes.

- def distances_bellman_ford(problem: np.ndarray, start: int) -> tuple[list[int], list[float], set[int]]:
	Takes the weighted adjacency matrix `problem` (use `np.inf` for absent edges) and a source node `start`. Returns `(predecessors, distances, negative_nodes)`:
	- `distances[v]` is the minimum distance from `start` to `v` when no reachable negative cycle can affect `v`; if `v` is unreachable, it remains `np.inf`.
	- `predecessors[v]` is the previous node on one shortest path to `v`
	- `negative_nodes` is the set of vertices that lie on or are reachable from a negative‑weight cycle reachable from `start`.

- def shorthest_path_bellman_ford(predecessors, distances, end: int, negative_nodes) -> tuple[list[int], float]:
	Reconstructs a shortest path to `end` using the `predecessors` array. Returns `(None, np.inf)` if `end` is unreachable, `(None, -np.inf)` if `end` is affected by a negative cycle (in `negative_cycle`), otherwise returns `(path, cost)`. The reconstruction guards against cycles in the predecessor chain.


Comment: I found out today (21/11) that the assignment was to find the shortest positive path (not simply the lowest-cost path, which may be negative). I have not had time yet to design a smart solution. 

   
