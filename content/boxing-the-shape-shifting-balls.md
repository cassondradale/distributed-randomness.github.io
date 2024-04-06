+++
title = "The tale of binning the shape-shifting balls"
date = 2024-03-26
updated = 2024-03-26
draft = false
in_search_index = true

[taxonomies]
  tags = ["plb", "func", "ideas", "optimization"]
  categories = ["plb"]

[extra]
math = true
+++

## The plot
There are two characters in this story - the _balls_, and the _bins_. Balls like to stay in the bins but
a bin can only accommodate so many balls at a time. Thank goodness there are many bins. And there is
_karma_. It maintains order in the world of balls and bins - making sure there are enough bins but not
too many and all balls in a bin has sufficient room to breathe. It uses its _power wand_ to maintain
the order. There are two types of power actions:
1. `map`: under which take a ball or a bin and transforms them into one or more of the same
   kind (ball maps to a list of one or more balls and so does the bins).
1. `place`: take a list of balls and bins and arrange balls into the bins.

And there is variety in this world. There are different kinds (or shapes) of balls, bins. Similarly,
`map` and `place` have their unique kinds as well.

## Formalism
Now let's formalize this world so that karma can be adept at maintaining its order. So, we have sets
of balls ($A$) and bins ($B$). Similarly, map ($M$) and place($P$) are sets of functions.

_map_ is function that takes a list of object and returns another list of objects.
This creates possibility of taking a red ball and split it into 3 green balls, for example. But the
power to convert a ball to bin or a bin to ball does not exist.

$$
M: [X] \to [X']' \space\space X \in {A, B}
$$

_place_ is function that takes a list of balls and bins and returns a list of list of balls, where
each inner list belongs the balls that are to be placed in that bin.

$$
P: ([A], [B]) \to [[A]_1, [A]_2, .. B \space times]
$$

map and place are composable. So, say in a toy world, we have the balls a1, a2, a3 and bins b1, b2.
Then we can do

$$
p(m([a1]), m([a2]), m([a3]), [b1, b2, b3])

where m()
$$
Say for example the use of power in the above way gives us this arrangement:

$$
[[a11, a2],  [], []]
$$


Because Karma just, it must use this power for some objective and here the objective is to minimize
the number of bins and the number of powers used.

