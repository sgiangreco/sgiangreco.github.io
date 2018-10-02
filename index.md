## Week 6 - 9/23/18

  I spent most of this week studying for a couple of exams and preparing for my university's semi-annual career fair.  I was therefore unable to spend much time creating prototypes of algorithms I had learned about in the previous week.  However, I did manage to glance through much of chapter three in _Stochastic Local Search_ and found that it mostly discusses the modeling of local searches with generalized local search machines (GLSMs).  I am not quite sure at this time how useful it will be to know how the algorithms work from the formal perspective of finite state machines, so I will try to read the chapter more in depth when I get a chance.
  
  I was able to create a presentation on the different stochastic local search algorithms from chapter 2 and deliver my findings to my research team.  The slideshow can be found [here](https://github.com/sgiangreco/Intro-to-Stochastic-Local-Search).
  
  For this week, my main focus will be on creating a functioning SAT iterative improvement algorithm.  I expect that, once I am able to write that, the difficulty in crafting more sophisticated methods will greatly reduce, at least in terms of ensuring the SAT problem's information is properly parsed and evaluated.  As I move on to more complex non-population based methods, the true challenge would then lie in constructing and implementing the search algorithms and pertubation mechanisms.

## Week 5 - 9/16/18

  I have finished reading over the second chapter of the _Stochastic Local Search_ book.  This chapter went into greater depth on basic types of stochastic local search algorithms.  This began with detailing a few iterative improvement methods, but the weakness of stagnating in a local optimum quickly became apparent in these algorithms, so a greater focus on diversification of searches took hold.  To increase the diversity of solutions, randomness was introduced in a variety of ways.  Finding the right mixture of deterministic improvement and chance became a key component in these more sophisticated solvers.  Since improved performance is always in demand, later methods started to include adaptive components for regulating the amount of randomness introduced to the search steps as candidate solutions evolve.  The chapter concluded with population-based methods which feature adapting mechanisms dependent on the co-evolution of parallel solver instances running on the same problem.

  As I mentioned last week, our university hosted a Research and Development conference Monday and Tuesday of this week.  There I attended a lecture on Python for Machine Learning presented by Amit Gupta of the Texas Advanced Computing Center (TACC).  The talk went over different packages in Python used for various mathematical applications and touched on a couple of machine learning methods.  I was also able to listen to Dave Morton of the Los Alamos National Laboratory discuss the implementation of high performance computing at his workplace as well as some of the challenges it has and continues to pose.

  Over the course of the coming week, I hope to begin coding some of the examples I encountered in the book and to continue reading through chapter 3.


## Week 4 - 9/9/18

  I have begun reading through _Stochastic Local Search - Foundations and Applications_ by Hoos and Stuetzle.  It introduced the propositional satisfiability (SAT) and Traveling Salesman problem (TSP) as prototypical combinatorial problems.  I have also begun reading about different basic iterative methods for effectively exploring a search space and how they compare to each other.  Examples are best improvement, first improvement, variable neighborhood descent (VND), and variable depth search (VDS).

  Next week, I will continue reading through the book and attempt to start writing code for some of the basic methods I encounter so as to help ferment my understanding.  I will also attend some presentations on high performance computing at our university's Research and Technology Development conference.


## Week 3 - 9/2/18

  I have continued expanding on the literature I've reviewed in SAT solvers.  Of particular importance is the [master's thesis by Alex Bertels](http://scholarsmine.mst.edu/cgi/viewcontent.cgi?article=8548&context=masters_theses), whose work inspired this research project.  The paper compares synchronous and asynchronous parallelization methods for evolving hyper-heuristics and finds that the latter have significantly greater performance.  The paper also introduces two versions of the Automated Design of SAT Solvers employing Evolutionary Computation (ADSSEC) framework, an implementation of evolutionary algorithms on improving hyper-heuristics.  The later version was able to outperform top CDLCL solvers and yielded the discovery that having fewer decisions and conflict literals does not necessarily increase the performance of the solver.  The work done here serves as a major jumping-off point for our project, and a thorough understanding of this work may prove instrumental in further developing hyper-heurstics.

  It was suggested at our group meeting that I begin reading the book [_Stochastic Local Search - Foundations and Applications_ by Hoos and Stuetzle](http://www.sls-book.net/) to gain a greater understanding of how local searches are selected and performed in combinatorial problems.  My goal next week will be to focus on reading the book and familiarizing myself with local search algorithms.


## Week 2 - 8/26/18

  I mostly focused this week on expanding my understanding of propositional satisfiability.  One paper I read, [_The Automated Design of Variable Selection Heuristics for CDCL Solvers to Target Problem Classes_](https://web.mst.edu/~tauritzd/pubs/2017/Illetskova2017.html), discussed an attempt at applying evolutionary algorithms to create SAT solvers for specific types of problems.  The results were promising, as evolved solvers were able to outperform existing conflict-driven clause learning (CDCL) solvers such as [Glucose](http://www.labri.fr/perso/lsimon/glucose/).  Much of my work this coming year will focus on improving the evolutionary algorithms, so the ability to compare results so readily will be of great use.

  For the coming week, I plan to continue reading up on research done in SAT solvers as I try to gain a deeper understanding of how they can be improved.


## Week 1 - 8/19/18

  This week I begin working on this project, Scalable Automated Tailoring of SAT Solvers.  I set up my lab workstation, but it turns out that I have not yet been issued a key for the lab.  I was also introduced to some of the other students in the lab.  I reviewed the CREU project proposal and began making plans for ensuring that I would be able to keep up with the busy progress schedule.

  This coming week, I intend to read some research papers pertaining to SAT solvers and to get my own lab key.

