# Axelrod-model
The Axelrod_model.ipynb file is a Jupyter notebook from the Anaconda project to recreate the Axelrod model from the paper titled "The Dissemination of Culture", published by SagePublications on 1997.

Here we try to analyze the evolution of culture, understood as any socially transmited aspect from the human life, through time. To do this, we represent a society as a matrix with real entries and we understand each entry as a person or a village.

Also we think the society to have n traits and m opinions per trait, so we asociate a vector of n entries to each individual in which each entry can take m options.

The algorithm for each iteration proposed by Axelrod is:
  1) Select a person from the society with a uniformly distributed random variable.
  2) Select one of its neighbors with a uniformly distributed random variable. Here we will understand as a neighbor, the individuals to the right, to the left, in front and at the back of the selected person.
  3) Calculate the similarity between the individual and its selected neighbor and take it as the probability for the two persons to interact.
  4) If they interact, randomly select a trait and set the opinion of the selected individual from that trait to the opinion from its neighbor from the same trait.
  
To represent this, we calculate the average similarity between each member from the society and its neighbors and print them into a graph where each square represent a individual. The darker the square is, the less the average similarity between the person and its neighbors is. On the opposite case, the clearer the square is, the more similar the person to its neighbors is.




On the other hand, the Axelrod_model_with_ideas_generation.ipynb has as objective the modification of the Axelrod model (available on this account) so it would be possible to simulate the society has new ideas.
This work was done using the notebooks from the jupyter project.

The algorithm to complete an iteration from our code is described on the following lines.

After concluding the Axolrod's algorithm, we select a person from our society (which we will call "thinker") with a uniformly probability distribution and select a random number "S", generated with a normal distribution, which will be interpreted as the thinker's receptivity.

Taking in mind we are thinking our society as the entries of some matrix M and seeing our system as a topological spqce, we define the ball with radius r and centered on a_{ij} as B(a_{ij},r)=\{b_{cd}\in M : |i-c|\leq r $ y $|j-d|\leq r\}.
Supposing the thinker is the person a_{ij}, we take B(a_{ij},0) and calculate the similarity between the persons in that ball and the thinker. If that similarity is grater than S, we take B(a_{ij},1) and repet the process. We will continue iteratively until the the calculated similarity is smaller than S and we will call that ball "B_{max}".

Once we have B_{max}, we will divide the number of persons inside that ball and the total number of people on our society, taking that number as th eprobability that the thinker will get influenced by the others.
Now we generate another random number "T" with a normal distribution and we will take it as the creativity of thinker, i.e. the probability that the thinker could have an idea.

If our thinker does have an idea, we will choose a random subject from our society and we will set the opinion from the thinker as the average opinion on that topic from the people inside B_{max}.

The examples shown on this repository are some examples of the behavior of the generation of ideas by this algorithm.


