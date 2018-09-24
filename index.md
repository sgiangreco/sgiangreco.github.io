## Week 1

I have begun reading through _Stochastic Local Search - Foundations and Applications_ by Hoos and Stuetzle.  
It introduced the propositional satisfiability (SAT) and Traveling Salesman problem (TSP) as prototypical combinatorial problems.  
I have also begun reading about different basic iterative methods for effectively exploring a search space and how they compare to each other.
Examples are best improvement, first improvement, variable neighborhood descent (VND), and variable depth search (VDS).

Next week, I will continue reading through the book and attempt to start writing code for some of the basic methods I encounter so as to help ferment my understanding.
I will also attend some presentations on high performance computing at our university's Research and Technology Development conference.


## Week 2

I have finished reading over the second chapter of the _Stochastic Local Search_ book.  This chapter went into greater depth on basic types of stochastic local search algorithms.  This began with detailing a few iterative improvement methods, but the weakness of stagnating in a local optimum quickly became apparent in these algorithms, so a greater focus on diversification of searches took hold.  To increase the diversity of solutions, randomness was introduced in a variety of ways.  Finding the right mixture of deterministic improvement and chance became a key component in these more sophisticated solvers.  Since improved performance is always in demand, later methods started to include adaptive components for regulating the amount of randomness introduced to the search steps as candidate solutions evolve.  The chapter concluded with population-based methods which feature adapting mechanisms dependent on the co-evolution of parallel solver instances running on the same problem.

As I mentioned last week, our university hosted a Research and Development conference Monday and Tuesday of this week.  There I attended a lecture on Python for Machine Learning presented by Amit Gupta of the Texas Advanced Computing Center (TACC).  The talk went over different packages in Python used for various mathematical applications and touched on a couple of machine learning methods.  I was also able to listen to Dave Morton of the Los Alamos National Laboratory discuss the implementation of high performance computing at his workplace as well as some of the challenges it has and continues to pose.

Over the course of the coming week, I hope to begin coding some of the examples I encountered in the book and to continue reading through chapter 3.
