% Define facts about fruits and their colors
fruit_color(apple, red).
fruit_color(banana, yellow).
fruit_color(grape, purple).
fruit_color(orange, orange).
fruit_color(plum, purple).
fruit_color(strawberry, red).
fruit_color(blueberry, blue).

% Define a predicate to find the color of a fruit
get_fruit_color(Fruit, Color) :- fruit_color(Fruit, Color).

% Define a predicate to find all fruits of a given color using backtracking
fruits_of_color(Color, Fruits) :- findall(Fruit, fruit_color(Fruit, Color), Fruits).
% ?- get_fruit_color(apple, Color).
% ?- fruits_of_color(purple, Fruits).
