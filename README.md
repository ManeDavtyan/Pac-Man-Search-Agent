# Pac-Man-Search-Agent

## Introduction
This paper takes as an area of research the original game and a series of modifications of
Pac-Man as a problem-solving environment to deep dive into the state-space search, and other
algorithms, covered during our course CS246, "Introduction to Artificial Intelligence." By doing
so, we aim to define our problem as the enhancement of Pac-Man's behavior.
There are a couple of reasons behind our decision to concentrate on Pac-Man. Firstly, it is fun to
play and watch, as Pac-Man provides a point in history where video games moved into new
territory(Thompson et al., 2008) and perfectly represents retro pop culture. Secondly, this
environment supports deterministic/stochastic, fully/partially observable, and adversarial
problem settings. Finally, this is an environment that is both intuitive and rich (DeNero & Klein).
Pac-Man is intuitive because it consists of objects moving around on a grid; this setting is easy to
map onto the general definitions of search problems. Pac-Man is rich because it gives rise to very
challenging AI problems.
The main goal of this project is to examine and test methods for the enhancement of Pac-Man's
behavior. First, we will represent Pac-Man as a single-agent search problem with several search
algorithms and compare the performance of Pac-Man in terms of the algorithm's performance,
completeness, and optimality. Second, we will discuss more complicated modifications of
Pac-Man (i.e., including nondeterministic ghosts, etc.) and methods that have been used to solve
and improve them. Therefore, the paper will consist of two parts. The first part will discuss the
original Pac-Man, its modifications, and methods that have been used to solve and improve
them, and the second part will concentrate on the methods and solutions for Pac-Man as a
single-agent search problem.
## Literature Review
Pac-Man was developed by Toru Iwatani and was released by Namco as a coin-operated arcade
game in 1980. The game was initially called Puckman but was renamed and redistributed in
America by 1981. It soon became the most popular arcade game of all time, even causing a coin
shortage in Japan.
3
Pac-Man
Based on the “Pac-Man Conquers Academia: Two Decades of Research Using a Classic Arcade
Game” paper, you can see the game rules and description below. (Rohlfshagen, Perez-Liebana,
n.d.)
● The game is played on a 2-dimensional maze.
● The player uses the four-way joystick to guide Pac-Man through the maze.
● 240 (non-flashing) pills worth 10 points, 4 (flashing) power pills worth 50 points along
the maze.
● The lair in the middle of the maze, where the four ghosts begin, is where they are all free
one at a time.
● As each ghost chases Pac-Man, they eat him at first contact.
● Initially, Pac-Man has two extra lives; the game ends when all lives are gone.
● At 10,000 points, a new life is awarded.
● When Pac-Man consumes a power pill, the ghosts temporarily turn blue and become
edible for a short while.
● After eating four ghosts in a row, Pac-Man receives a score that doubles: 200, 400, 800,
and 1,600.
● 3 050 points can be obtained per power pill eaten (3000 points for eating all the ghosts +
50 points for the power pill)
● Bonus fruits occasionally appearing right below the lair are the final way to get points.
● Eight different fruits range from 100 to 5,000 in value (higher-valued fruits appear in
later levels only).
● Pac-Man is the player of the game
● Ghosts are the enemies of the general hero
○ There are four main ghosts in the game; red Blinky, pink Pinky, blue Inky, and
orange Clyde
○ In the original game, ghosts have deterministic behavior intended to consume the

## Method
The Pac-Man agent will find paths through his maze world, both to reach a particular location
and to collect non-flashing pills efficiently. We will build general search algorithms such as BFS,
DFS, UCS, A* and apply them to Pacman scenarios. We will compare the performance of
Pac-Man in terms of the algorithm's performance, completeness, and optimality.
Considering the fact that such experiments were done before, we will also compare our results
with the prior ones.
In order to develop an environment that includes mazes of different sizes, non-flashing pills, and
our moving agent Pac Man we will use Python 2.7 programming language. Code sources for
creating the environment are available online, provided by the University of California,
Berkeley, in the scope of the course CS188, Introduction to Artificial intelligence; hence we are
planning to use them as well as to perform modifications in order to get different mazes. After
we implement the search algorithms, we will use those on the developed environment with the
modified mazes and compare the eventual results with the initial ones.
About the Structure of Files (Provided by UC, Berkeley)
The code for this project consists of several Python files. (Joshkarlin, n.d.)
Files to edit:
search.py , Where all of the search algorithms will reside.
searchAgents.py , Where all search-based agents will reside.
Files you might want to look at:
pacman.py The main file that runs Pacman games. This file describes a Pacman GameState
type, which you use in this project.
game.py The logic behind how the Pacman world works. This file describes several
supporting types like AgentState, Agent, Direction, and Grid.
util.py Useful data structures for implementing search algorithms.
Supporting files:
graphicsDisplay.py Graphics for Pacman
graphicsUtils.py Support for Pacman graphics
textDisplay.py ASCII graphics for Pacman
ghostAgents.py Agents to control ghosts
keyboardAgents.py Keyboard interfaces to control Pacman
layout.py Code for reading layout files and storing their contents
9
## Evaluation
To find the optimal path through the maze we have considered solving the problem with the help
of a problem-solving agent, to let the agent eat all the dots in fewer steps possible. In designing
this intelligent agent, we implemented various uninformed search algorithms covered during the
semester. (DFS, BFS, UCS). Although these algorithms can solve the problems, they are not that
efficient; thus, we have applied informed search as well. (A* search with heuristics Manhattan
distance and Euclidian distance)
We have run all the mentioned searches and recorded the number of expanded nodes, scores, and
total cost while defining our main agent to be the Pac-Man. We have also included several pills
(goals) throughout the maze, thus doing the Pac-Man search for them. For this certain reason, we
have added new classes for each of the search algorithms to collect all the pills in the maze. In
our code, the A* search was run by two heuristic functions, with Manhattan and Euclidian
distances. Besides, we have generated new mazes of three different sizes, tiny, medium, and big,
and run the searches on both the original and newly generated mazes. The mazes were generated
by the online tool cited below. (dCode, n.d.)

## Conclusion
In a nutshell, in our final project, we have discovered the historical background of the
well-known arcade game Pac-Man. We have analyzed various methods for creating Pac-Man
controllers and scientific works conducted based on those methods. Afterward, we inspected the
game in the sense of a problem-solving environment. Our group applied uninformed and
informed searches to define the performance of Pac-Man, and we defined pills all over the maze
as our goal states. As a result, out of all search algorithms, we have found that the BFS, UCS,
and A* searches have exactly the same total scores and solution costs. Such as, BFS is a specific
case of UCS, when all its path costs are equal, they perform exactly the same, and for the A*
search turned out that the heuristics do not change results in this case. Meanwhile, the A* search
has expanded less nodes compared to BFS and UCS. Scores generated by DFS are more or else
similar to the scores generated by the other search algorithms. Although, the DFS expands the
least amount of nodes out of all searches. Thus, in a sense of space, DFS is the best-performing
search, while the A* is the best one in a sense of achieving the goal with the higher score
possible, and less number of nodes expanded


## References:

A. Fitzgerald and C. Congdon, "RAMP: a Rule-based Agent for Ms. Pac-Man," in Evolutionary
Computation, 2009. CEC’09. IEEE Congress on. IEEE, 2008, pp. 2646–2653.
A. Kalyanpur and M. Simon, "Pacman using Genetic Algorithms and Neural Networks,"
Retrieved from http://www.ece.umd.edu/˜adityak/Pacman.pdf (19/06/03), 2001.
dCode. (n.d.). Maze Generator (perfect) - online text ASCII Labyrinth. (Perfect) - Online Text
ASCII Labyrinth. Retrieved December 10, 2022, from https://www.dcode.fr/maze-generator
DeNero, J., & Klein, D. (n.d.). (working paper). Teaching Introductory Artificial Intelligence
with Pac-Man.
DeNero, J., Klein, D., & Abbeel, P. (n.d.). The Pac-Man Projects. Berkeley Ai Materials.
Retrieved November 7, 2022, from http://ai.berkeley.edu/project_overview.html
Joshkarlin. (n.d.). Joshkarlin/CS188-project-1: In this project, your Pacman agent will find paths
through his maze world, both to reach a particular location and to collect food efficiently. you
will build general search algorithms and apply them to Pacman scenarios. GitHub. Retrieved
December 10, 2022, from https://github.com/joshkarlin/CS188-Project-1
J. Koza, Genetic Programming: On the Programming of Computers by Means of Natural
Selection. MIT Press, 1992.
M. Gallagher and M. Ledwich, "Evolving Pac-Man Players: Can We Learn from Raw Input?"
Computational Intelligence and Games, 2007. CIG 2007. IEEE Symposium on, pp. 282–287,
2007.
M. Gallagher and A. Ryan, "Learning to play Pac-Man: an evolutionary, rule-based approach,"
Evolutionary Computation, 2003. CEC’03. The 2003 Congress on, vol. 4, 2003.
N. Tziortziotis, K. Tziortziotis, and K. Blekas, "Play Ms. Pac-Man using an Advanced
Reinforcement Learning Agent," in Hellenic Conference on Artificial Intelligence. Springer,
2014,
Project 1: Search in Pacman. (n.d.). Retrieved November 14, 2022, from
https://inst.eecs.berkeley.edu/~cs188/sp11/projects/search/search.html
18
Rohlfshagen, P., Perez-Liebana, D., Liu, J., & Lucas, S. M. (n.d.). Pac-Man Conquers Academia:
Two Decades of Research Using a Classic Arcade Game. Retrieved November 7, 2022, from
http://www.diego-perez.net/papers/PacManConquersAcademia.pdf
S. Lucas, "Evolving a neural network location evaluator to play ms. pac-man," Proceedings of
the IEEE Symposium on Computational Intelligence and Games, pp. 203–210, 2005.
Thompson, T., McMillan, L., Levine, J., & Andrew, A. (2008). An evaluation of the benefits of
lookahead in pac-man. 2008 IEEE Symposium On Computational Intelligence and Games.
https://doi.org/10.1109/cig.2008.5035655
T. Mott, 1001 Video Games You Must Play Before You Die. Cassell Illustrated, 2010.
