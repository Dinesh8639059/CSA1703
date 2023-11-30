% Define the graph (adjacency relations between nodes)
connected(nodeA, nodeB, 5).
connected(nodeA, nodeC, 10).
connected(nodeB, nodeD, 15).
connected(nodeC, nodeD, 5).
connected(nodeB, nodeE, 20).
connected(nodeD, nodeE, 10).

% Goal state: We want to reach nodeD
goal(nodeD).

% best_first_search(Start, Path)
best_first_search(Start, Path) :-
    best_first_search([Path], Start, []).

% Base case: We've reached the goal
best_first_search([Goal|_], Goal, _).

% Recursive case: Expand the current path
best_first_search([Path|Paths], Goal, Visited) :-
    extend(Path, NewPaths),
    subtract(NewPaths, Visited, UnvisitedPaths),
    append(Paths, UnvisitedPaths, AllPaths),
    sort_paths(AllPaths, SortedPaths),  % Sort paths by heuristic value
    best_first_search(SortedPaths, Goal, [Path|Visited]).

% Extend a path to its neighboring nodes
extend([Current|Path], NewPaths) :-
    connected(Current, Neighbor, _),
    \+ member(Neighbor, Path),
    extend([Neighbor, Current|Path], NewPaths).
extend(Path, [Path|[]]).

% Sort paths by heuristic value
sort_paths(Paths, SortedPaths) :-
    predsort(compare_paths, Paths, SortedPaths).

% Compare paths by heuristic value
compare_paths(Order, Path1, Path2) :-
    heuristic_value(Path1, H1),
    heuristic_value(Path2, H2),
    (H1 =< H2 -> Order = '<'; Order = '>').

% Define a heuristic function to estimate the cost to reach the goal
heuristic_value([City|_], H) :-
    goal(Goal),
    connected(City, Goal, H).

% Find the optimal path
find_optimal_path(Start, OptimalPath) :-
    best_first_search(Start, Path),
    goal(Goal), % Ensure Goal is defined
    Path = [Start|_],
    last(Path, Goal),
    OptimalPath = Path.
