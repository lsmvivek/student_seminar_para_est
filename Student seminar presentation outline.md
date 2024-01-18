Outline for my student presentation on 19th January, 2024. 
Topic: [[Metropolis Hastings]] Algorithm
Outline: Three parts
- [x] History of development of the algorithm
- [x] Theoretical background
- [x] Jupyter notebook for hands on

### **Theoretical background**
Let us have a non-linear (or linear) equation $f$ with 3 parameters, a, b & c.
Let us define the function $f$ first:
$$
f  =  x_1 \cdot exp(-a) + b \cdot x_2 + c
$$
And the parameters with the following space:

$$
\begin{aligned}
a \in [0,20] \\ 
b \in [0,1000] \\
c \in [0,50]
\end{aligned}
$$

Now we see the possible number of parameter combinations here is: $20 \times 1000 \times 50 = 1 million$. This is a fairly large number, if one were to do the estimation by manually changing the parameter set $\theta = [a,b,c]$, it would take a long time.
One may argue that brute force application will also work if the user generates all possible combinations and calculates the error of all of them. However, lets say there are more than 100 grids for which the parameters are to be estimated and the function $f$ is much more complicated then the one we have assumed above. It would result in heavy computational resource and precious time demands. 

To avoid such a situation, one can use the Metropolis Hastings Algorithm, to randomly sample from the complete parameter space and arrive at the best solution.

| p | probaibility |
| ---- | ---- |
| $\theta$ | state of parameters |
| $y$ | observed data |
| $p(\theta)$ | prior |
| $p(x\|\theta)$ | likelihood |
| $p(x)$ | Normalisation |
| $p(\theta\|x)$ | posterior |
### **History of development of the algorithm**
* 1949: Developed by Nicholas Metropolis, who also led the development of the first programmable super-computer MANIAC, speed of which allowed the MC method to be developed.
* The Monte Carlo (*the first MC*) method was developed to *simulate* the behaviour of neutrons in a fissile material in atomic bombs. [The Monte Carlo Method; Metropolis and Ulam 1949,](https://doi.org/10.1080/01621459.1949.10483310)
* 1970: Followed by W. Keith Hastings among others, in showed the true potential of the algorithm as a method to sample from high-dimensional probability distributions.
* Hastings generalized the algorithm to use with non-symmetrical distributions. Also introducing the proposal distribution as Markov chain (*the second MC*).
* 1990s, Gibbs sampling, a special case of the M-H algorithm became popular. Thus MCMC methods formally came into being.
Since then there have been numerous MCMC methods:
1. Rejection Sampling
2. Gibbs Sampling
3. Metropolis(-Hastings)
4. Slice Sampling
5. Stochastic Gradient Langevin Dynamics (SGLD)
6. Annealed Importance Sampling (AIS)
7. And more!
*Reference: A History of the Metropolis–Hastings Algorithm; DOI: 10.1198/0003130032413*
###  Jupyter notebook for hands on
