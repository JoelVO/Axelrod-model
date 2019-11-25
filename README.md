# Axelrod-model
This is a program made in Jupyter notebook from the Anaconda project to recreate the Axelrod model from the paper titled "The Dissemination of Culture", published by SagePublications on 1997.

Here we try to analyze the evolution of culture, understood as any socially transmited aspect from the human life, through time. To do this, we represent a society as a matrix with real entries and we understand each entry as a person or a village.

Also we think the society to have n traits and m opinions per trait, so we asociate a vector of n entries to each individual in which each entry can take m options.

The algorithm for each iteration proposed by Axelrod is:
  1) Select a person from the society with a uniformly distributed random variable.
  2) Select one of its neighbors with a uniformly distributed random variable. Here we will understand as a neighbor, the individuals to the right, to the left, in front and at the back of the selected person.
  3) Calculate the similarity between the individual and its selected neighbor and take it as the probability for the two persons to interact.
  4) If they interact, randomly select a trait and set the opinion of the selected individual from that trait to the opinion from its neighbor from the same trait.
  
To represent this, we calculate the average similarity between each member from the society and its neighbors and print them into a graph where each square represent a individual. The darker the square is, the less the average similarity between the person and its neighbors is. On the opposite case, the clearer the square is, the more similar the person to its neighbors is.
