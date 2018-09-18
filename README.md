# Cross-docking Scheduling Problems

In this repository, you will find the codes and instances used in the articles:

#### A hybrid Lagrangian metaheuristic for the cross-docking flow-shop scheduling problem. Fonseca, G.B.;  Nogueira, T.H. and Ravetti, M.G. Submitted, 2018.
#### Cota, P. M. ; Gimenez, B.M.R. ; Araujo, D. P.M. ; Nogueira, T.H. ; Souza, M.C.; Ravetti, MG. Time-indexed formulation and polynomial time heuristic for a multi-dock truck scheduling problem in a cross-docking centre. Computers & Industrial Engineering, v. 95, p. 135-143, 2016.

## Algorithms

The programming language used is C++ with the optimization software CPLEX 12.4. 

### The Lagrangian algorithm for the 2-dock problem:

We propose a hybrid method based on a Lagrangian relaxation technique through the volume algorithm for the 2-dock problem. The program reads the number of jobs (n and m), two vectors composed by the processing times (machine 1 and machine two, respectively) and one matrix of precedence.

Download algorithm: [RLg.cpp](https://drive.google.com/open?id=1qRbW0pOnw5ViAJw7TGQoGJvI-TuVOW6T) 

### Constructive Heuristics:

The Constructive Heuristics H1 and H2 use information from Lagrangian multipliers to sort jobs. In the final step both heuristics use an NEH-like heuristic to construct the feasible solution.

Download algorithm: [HeuristicaConstrutiva.cpp](https://drive.google.com/open?id=1glHzPxjKX1F5NnUSlUe3d1A2QroSXGDN) 

### JB Heuristic:

We programmed the best heuristic introduced by Chen and Lee (2009), which is based on Johnson's algorithm. The NEH algorithm and Local search are used to refine the results of JB in the same way than used in H1 and H2.

Download algorithm: [HeuristicaConstrutiva.cpp](https://drive.google.com/open?id=1glHzPxjKX1F5NnUSlUe3d1A2QroSXGDN)

### CDH Heuristic:

Next you find the CDH heuristic proposed by Cota et al. (2016). The CDH heuristic starts by creating a preliminary schedule in the second machine. With this, a schedule is defined in the first machine and finally the second machine is rescheduled.

Download algorithm: [main.cpp](https://drive.google.com/open?id=1PcuGQ_M4ibWwXnQw-qFj9XyClj-0iaxD)

## Instances

### Instances for the 2-dock version:

The instances are composed by the number of jobs on machine 1, number of jobs on machine 2, processing times of the jobs on machine  1, 
processing times of the jobs on machine 2 and the matrix of precedence, that contain the list of jobs on machine 1 that are precedent on machine 2.

Example: [n5m3mp4_p1-10_1.txt](https://drive.google.com/open?id=15XWvWe4JYu8wDSuSJc8JCW8hmfTu3ui6)

5  
3  
7 4 7 2 10  
4 10 3  
3 2 3 4  
2 0 1  
1 1 

* The first line correspond to the number of jobs on machine 1 (n=5);
* The second line correspond to the number of jobs on machine 2 (m=3);
* The third line correspond to the processing times of the n jobs on machine  1, for example, the processing time of job 3 (consider jobs from 0 to 4) on machine 1 is 2.
* The fourth line correspond to the processing times of the m jobs on machine  2, for example, the processing time of job 1 (consider jobs from 0 to 2) on machine 2 is 10.
* From the fifth line onwards we represent the matrix of precedence. The matrix is composed by m lines corresponding to m jobs on machine 2. 
* For each job on machine 2, there is a corresponding subset of jobs on machine 1 (second column onwards). It is considered that each element job on machine 2 has at least one job on  machine 1 as precedent. 

For example: The first line on the matrix correspond to the first job on machine 2 (3 2 3 4). It means that the first job on machine 2 has three jobs on machine 1  as precedent (first element of the matrix). These jobs are job 2, job 3, and job 4 on machine 1. 

The same reasoning happens for other jobs on machine 2, for example,  the second line on the matrix correspond to the second job on machine 2. Note that the second job on machine 2 has two jobs on machine 1  as precedent (first element of the matrix). These jobs are job 0 and job 1 on machine 1. And so on for all m jobs.

It is important to note that we consider jobs varying from 0.

#### Group of instances:

The instances used in this work are divided into two groups. In each group of instances, n is fixed and the number m is randomly chosen from the range of [0.6n, 0.8n, 1.0n, 1.2n, 1.4n]. For each n, five instances with different m values are considered. And for each pair (n, m), we generate 10 different problems, therefore the benchmark consists of 500 instances. All instances are available below:

|Group| Files |
|:-------------:|:-------------:|
| 1 | [Grupo 1](https://drive.google.com/open?id=16QYVuQ6mG4ah-vHlVlF50OVgccPqZ7R6) |
| 2 | [Grupo 2](https://drive.google.com/open?id=1EUnx33BeLzZSotX5A2Hf_Amed1hPBlY6) |

### Instances for the multi-dock version:

Artificial instances were generated varying the number of jobs and machines. We consider values of n1 equal to 20, 30, 40, 50, 60, 70 and 80 jobs, and values of n2 equal to integers in [0.8n1, 1.2n1]. Five groups of instances were examined. The first three groups consider the same number of machines in each stage: 2, 4, and 10. The last two groups of instances use a random number of machines in each stage, selected from a uniform distribution U(2,4) and U(2,10), respectively. Processing times were generated with a uniform distribution U(10, 100). We generated 300 instances for each combination of number of jobs and number of machines, resulting in a total of 10.500 instances. All instances are available below:

|Group| Files |
|:-------------:|:-------------:|
| 1 | [2 machines](https://drive.google.com/open?id=1aRxy5rSmWWx4xVreV26FrJw26EMzNMxg) |
| 2 | [4 machines](https://drive.google.com/open?id=1l8pteh9JCHMBPDClyclHwAAcrWBpRqKD) |
| 3 | [10 machines](https://drive.google.com/open?id=1V8j__8XVVr0fFwPDp7DLfdv703mEEKp2) |
| 4 | [U(2,4) machines](https://drive.google.com/open?id=1tZ4HQR4nxlKmQ1AM3NIv8EKsbm_9MD8X) |
| 5 | [ U(2,10) machines](https://drive.google.com/open?id=1kOJEsbhkr9L51OBkzt3OnNJaAzZwYYwo) |


Contact information

Gabriela Braga Fonseca - gabrielabragafonseca@gmail.com

Thiago Henrique Nogueira - thiagoh.nogueira@ufv.br

Martín Gómez Ravetti - martin.ravetti@dep.ufmg.br

