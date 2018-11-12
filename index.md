# Week 12 - 11/10/18
## DPLL solver
This week I have begun creating a conflict-driven clause learning (CDCL) solver using the [Davis-Putnam-Logemann-Loveland (DPLL) algorithm](https://dl.acm.org/citation.cfm?id=368557).  
This method is essentially of a constructive search comprised of unit propogation followed by some sort of variable selection.  
Unlike the other solvers I have encountered up to this point, this method iteratively replaces clauses with their resolvents after variable assignments, causing satisfaction to occur when all clauses become empty.

I had original set out to construct the [Davis-Putnam (DP) algorithm](https://dl.acm.org/citation.cfm?coll=GUIDE&dl=GUIDE&id=321034), but it does not appear to contain any way to backtrack out of conflicts.  
Additionally, both methods seem to lack a selection process for the variable assignment after unit propogation options have been exhausted.  
I plan to implement a random walk initially, but I am curious to see how more sophisticated stochastic local search methods will fare when coupled with this method.  
Changing the evaluation functions to focus on aiding unit propogation may also yield interesting results.

With the introduction of backtracking to a constructive search algorithm, a complete search can be created.  
However, that may come with a prohibitively high performance cost (particularly on problems with a large number of variables).  
I am not yet sure how to best proceed with tackling this issue, so I will at least for the moment use a complete search with smaller data sets.  

## SAT Graphing
To assist comprehension of differences between SAT problem classes, I will create graphs of various problem instances.  
By observing unique characteristics separating the problem classes, I hope to better identify primitives that could significantly affect heuristic selections.  
I will be using [SATGraf](https://bitbucket.org/znewsham/satgraf/) for this purpose.

# Week 11 - 11/3/18
The focus of this week has shifted to reading about the primitives that comprise most SAT solver algorithms.  
I began by reading through more of chapter 6 in the _Stochastic Local Search_ book to better familiarize myself with many of the methods discussed in comteporary research.  
It introduced me to the WalkSAT architecture, which differentiates itself immediately from GSAT with its evaluation function.
For solver algorithms of this variety, the evaluation function contains two steps.  
First, an unsatisfied clause _c_ under the current assignment _a_ is selected.  
Second, a variable corresponding to a literal in _c_ is flipped, causing the _c_ to become satisfied (for each clause is composed of disjunctions).  
The mechanism by which this variable is selected varies with each type of WalkSAT algorithm.

I then began reading some research papers by Alex Fukunaga.  
The first one, [_Automated Discovery of Local Search Heuristics for Satisfiability Testing_](https://ieeexplore.ieee.org/abstract/document/6792408), discusses how many of the algorithms I have so far encountered in my readings can be considered composites of basic heuristics called primitives.  
Identifying and properly combining these primitives lies at the heart of our project's research, so a deep understanding of this work may prove vital to our progress.


# Week 10 - 10/27/18
I have constructed a tabu search SAT solver that uses the 
Here is a [link](https://github.com/sgiangreco/probabilistic-iterative-improvement/blob/master/SAT%20-%20Probabilistic%20Iterative%20Improvement.ipynb) to the Jupyter notebook for the probabilistic iterative improvement method.

# Week 9 - 10/20/18
  On Monday, I presented my first iterative improvement SAT solver using the dataset found in the same repository.  I have also continued working on the probabilistic iterative improvement solver and am attempting to ensure the solvers work for larger amounts of data.  An interactive interface that takes in solver parameters and filenames for datasets will also be added to both solvers.

My reading of _Stochastic Local Search_ continues in chapter 6.  I am hoping to get through it by next week.

# Week 8 - 10/13/18
  This week I have finally completed the SAT solver using the [first iterative improvement algorithm](https://github.com/sgiangreco/first-iterative-improvement).  It takes in an input file following the DIMACS graph format for conjunctive normal form (CNF) and encodes the literals in each clause such that their corresponding variable and negation values can be deduced with bitwise operations.  A random assignment of the variable truth values is then created, and the 1-exchange neighbors of this current assignment are evaluated for any increase in the number of clauses satisfied.  At the first instance of such an improvement being located, its corresponding assignment then becomes the current variable assignment.  If no improvement can be made by any of the neighboring assignments, then a neighbor that does not decrease the number of satisfied clauses is randomly selected.  This process is then repeated until all clauses are satisfied or an improvement has not been found for a given number of times in a row.  The output of the solver shows the assignment of the current iteration, the index of the variable being exchanged when evaluating a neighbor, and the change in clauses satisfied by that neighbor.

I will be presenting my solver to my fellow researchers next week.  After that, I intend to create a probabilistic iterative improvement algorithm wherein the likelihood of a neighboring assignment being selected correlates directly with the increase in clauses satisfied.  I also will begin reading through chapter 6 of the _Stochastic Local Search_ book and try to find a way of implementing interactive code in my blogs so that readers may more easily observe my progress.

# Week 7 - 10/6/18
  I worked on developing the SAT solver prototype for the iterative improvement algorithm.  Unfortunately, progress is slow, but I am hoping that I can put in more hours in this following week to get the program running by next week.

# Week 6 - 9/29/18

  I spent most of this week studying for a couple of exams and preparing for my university's semi-annual career fair.  I was therefore unable to spend much time creating prototypes of algorithms I had learned about in the previous week.  However, I did manage to glance through much of chapter three in _Stochastic Local Search_ and found that it mostly discusses the modeling of local searches with generalized local search machines (GLSMs).  I am not quite sure at this time how useful it will be to know how the algorithms work from the formal perspective of finite state machines, so I will try to read the chapter more in depth when I get a chance.
  
  I was able to create a presentation on the different stochastic local search algorithms from chapter 2 and deliver my findings to my research team.  The slideshow can be found [here](https://github.com/sgiangreco/Intro-to-Stochastic-Local-Search).
  
  For this week, my main focus will be on creating a functioning SAT iterative improvement algorithm.  I expect that, once I am able to write that, the difficulty in crafting more sophisticated methods will greatly reduce, at least in terms of ensuring the SAT problem's information is properly parsed and evaluated.  As I move on to more complex non-population based methods, the true challenge would then lie in constructing and implementing the search algorithms and pertubation mechanisms.

# Week 5 - 9/22/18

  I have finished reading over the second chapter of the _Stochastic Local Search_ book.  This chapter went into greater depth on basic types of stochastic local search algorithms.  This began with detailing a few iterative improvement methods, but the weakness of stagnating in a local optimum quickly became apparent in these algorithms, so a greater focus on diversification of searches took hold.  To increase the diversity of solutions, randomness was introduced in a variety of ways.  Finding the right mixture of deterministic improvement and chance became a key component in these more sophisticated solvers.  Since improved performance is always in demand, later methods started to include adaptive components for regulating the amount of randomness introduced to the search steps as candidate solutions evolve.  The chapter concluded with population-based methods which feature adapting mechanisms dependent on the co-evolution of parallel solver instances running on the same problem.

  As I mentioned last week, our university hosted a Research and Development conference Monday and Tuesday of this week.  There I attended a lecture on Python for Machine Learning presented by Amit Gupta of the Texas Advanced Computing Center (TACC).  The talk went over different packages in Python used for various mathematical applications and touched on a couple of machine learning methods.  I was also able to listen to Dave Morton of the Los Alamos National Laboratory discuss the implementation of high performance computing at his workplace as well as some of the challenges it has and continues to pose.

  Over the course of the coming week, I hope to begin coding some of the examples I encountered in the book and to continue reading through chapter 3.


# Week 4 - 9/15/18

  I have begun reading through _Stochastic Local Search - Foundations and Applications_ by Hoos and Stuetzle.  It introduced the propositional satisfiability (SAT) and Traveling Salesman problem (TSP) as prototypical combinatorial problems.  I have also begun reading about different basic iterative methods for effectively exploring a search space and how they compare to each other.  Examples are best improvement, first improvement, variable neighborhood descent (VND), and variable depth search (VDS).

  Next week, I will continue reading through the book and attempt to start writing code for some of the basic methods I encounter so as to help ferment my understanding.  I will also attend some presentations on high performance computing at our university's Research and Technology Development conference.


# Week 3 - 9/8/18

  I have continued expanding on the literature I've reviewed in SAT solvers.  Of particular importance is the [master's thesis by Alex Bertels](http://scholarsmine.mst.edu/cgi/viewcontent.cgi?article=8548&context=masters_theses), whose work inspired this research project.  The paper compares synchronous and asynchronous parallelization methods for evolving hyper-heuristics and finds that the latter have significantly greater performance.  The paper also introduces two versions of the Automated Design of SAT Solvers employing Evolutionary Computation (ADSSEC) framework, an implementation of evolutionary algorithms on improving hyper-heuristics.  The later version was able to outperform top CDLCL solvers and yielded the discovery that having fewer decisions and conflict literals does not necessarily increase the performance of the solver.  The work done here serves as a major jumping-off point for our project, and a thorough understanding of this work may prove instrumental in further developing hyper-heurstics.

  It was suggested at our group meeting that I begin reading the book [_Stochastic Local Search - Foundations and Applications_ by Hoos and Stuetzle](http://www.sls-book.net/) to gain a greater understanding of how local searches are selected and performed in combinatorial problems.  My goal next week will be to focus on reading the book and familiarizing myself with local search algorithms.


# Week 2 - 9/1/18

  I mostly focused this week on expanding my understanding of propositional satisfiability.  One paper I read, [_The Automated Design of Variable Selection Heuristics for CDCL Solvers to Target Problem Classes_](https://web.mst.edu/~tauritzd/pubs/2017/Illetskova2017.html), discussed an attempt at applying evolutionary algorithms to create SAT solvers for specific types of problems.  The results were promising, as evolved solvers were able to outperform existing conflict-driven clause learning (CDCL) solvers such as [Glucose](http://www.labri.fr/perso/lsimon/glucose/).  Much of my work this coming year will focus on improving the evolutionary algorithms, so the ability to compare results so readily will be of great use.

  For the coming week, I plan to continue reading up on research done in SAT solvers as I try to gain a deeper understanding of how they can be improved.


# Week 1 - 8/25/18

  This week I begin working on this project, Scalable Automated Tailoring of SAT Solvers.  I set up my lab workstation, but it turns out that I have not yet been issued a key for the lab.  I was also introduced to some of the other students in the lab.  I reviewed the CREU project proposal and began making plans for ensuring that I would be able to keep up with the busy progress schedule.

  This coming week, I intend to read some research papers pertaining to SAT solvers and to get my own lab key.

