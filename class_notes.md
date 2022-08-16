# Before the start

- Ask: who has written a class before? should be paired with someone who has not

# Introduction


End of intro
- We’ll show some code, and put it together and break it apart several times to illustrate how to make it practical to use, but flexible 
Then we’ll discuss how to do a similar thing at a research project level

# Chapter 1, classes

Before starting with the notebook
- We’ll start by looking at putting things together that belong together
- Kwy question: How do we know what does?

- We know data structures that groups data together, lists, dictionaries, etc; and modules and packages that organize code with a similar scope
- Here we’ll look at functions and classes as a way to group data and functionality together in a way that is easy to use but remain flexible to changes




Exercises
- intro

# smells
# current_i, current_j, sigma_i, sigma_j needed all over the place
# not efficient: mgrid calculated every time
# defining the parameters of a run is tedious: define all the single variables
# need to do the bookkeeping for i, j in case you want to create / simulate entire trajectories
# changing the next step probability is going to be trouble
# adding a new activation map requires adding a new piece to the code
# what if map_type is not any of the 3?



```
def evaluate_position(current_i, current_j, sigma_i, sigma_j, activation_map):
    size = activation_map.shape[0]
    next_step_map = next_step_probability(current_i, current_j, sigma_i, sigma_j, size)
    selection_map = compute_selection_map(next_step_map, activation_map)
    return selection_map[current_i, current_j]
```