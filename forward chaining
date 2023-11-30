% Define some rules

% Rule 1: If it's raining, then the grass is wet.
wet_grass :- raining.

% Rule 2: If John is studying and Mary is studying, then they are working hard.
working_hard :- studying(john), studying(mary).

% Define initial facts
raining.
studying(john).
studying(mary).

% Forward chaining
conclude(X) :- wet_grass, X = 'The grass is wet.'.
conclude(X) :- working_hard, X = 'John and Mary are working hard.'.

% Query for conclusions
?- conclude(Conclusion).
