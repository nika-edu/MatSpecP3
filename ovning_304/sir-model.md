## Exploring the SIR-model

Based on a huge simplified mathematical model, you will examine the propagation of an epidemic in a population by implementing the model in a Python program. The model calculates the number of susceptible, infectious and recovered number of individuals from one day to another. You may read about the model [here](https://www.maa.org/press/periodicals/loci/joma/the-sir-model-for-spread-of-disease-the-differential-equation-model), but most of it is not applicable for this task.

### The States

The state of an individual, at a given time, in the population is precisely one of

* $S$: Susceptible
* $I$: Infectious
* $R$: Recovered

An individual not been infected is susceptible, an infected individual is not susceptible and a recovered individual is neither susceptible nor contagious. An individual is recovered after a given time of beeing infectious.

#### The Data Representation

* $N$: Number of individuals in the population
* $a$: The time span an individual is contagious (days, in this example)
* $b$: A constant being related to the infectivity of the disease (the higher value, the more infectivity)

#### The Model

The number of individuals whith each status after $k$ days is denoted $S_k$, $I_k$ and $R_k$. The number develops from day to day following the model

* $S_{k+1}=S_k - b\cdot I_k\cdot S_k$
* $I_{k+1}=I_k + b\cdot I_k\cdot S_k-I_k/a$
* $R_{k+1}=R_k+I_k/a$

Suppose the starting values $N=1\,000\,000$, $S_0=999\,999$, $I_0=1$, $a=7$ and $b=2.0\cdot 10^{-7}$. Note that this is a hugely simplified model which may not be applicable in real world.

#### The Tasks

1. Describe each equation in the model above.
    

2. Implement the model in Python and present the outcome as three diagrams, respectively showing graphs of

    * the development of the number of individuals with each status as $b=2.0\cdot 10^{-7}$

    * the development of the number of individuals with each status as $b=1.7\cdot 10^{-7}$

    * the development of the number of individuals with each status as $b=2.3\cdot 10^{-7}$

      for a suitable number of days. Comment these graphs.
       


3. Present the progress of the number of individuals of each state with respect to time as $b=2\cdot 10^{-7}$, but with variation of the number of days an individual is contagious. Let $a$ take the value 6, 7 and 8, one value at a time. Comment the result.
    

4. Epidemiologs talk about "flattening the curve", [read more abut this topic here](https://en.wikipedia.org/wiki/Flattening_the_curve). Why is this important? Based on your results above, what is important to achieve?