# Improved heuristic task-to-thread mapping
This simulator performs task-to-thread mapping of OpenMP-based programs using heuristic and improved heuristic algorithms.
<br/>
<br/>
## Specification
The graphs can be generated in the simulator based on the benchmarks or randomly. The task execution time is calculated using the minimum, average, or maximum function. The application deadline is determined based on the volume of graph and a random number. For each method, the response time, missed deadline, idle time of threads, and static scheduling of tasks in threads are determined through the simulation process. Furthermore, graphical results can be generated to show the mapping of tasks. After mapping the graph using each algorithm, the response time, idle time, and missed deadline obtained from all the methods are exported to a file.
<br/>
<br/>
As the simulator is used to schedule the graphs generated based on benchmarks as well as the task execution times are high, the tick (e.g., time interval) of the loop in the codes is set to 1000000 (i.e., t += 1000000) by default. However, it can be set to 1 to simulate other benchmarks or random graphs.
<br/>
<br/>
## Simulation parameters
The simulation parameters are set by default. However, they can be changed at the beginning of simulation.py before the simulation process based on requirements of the application.
<br/>
<br/>
## Graphical output
Graphical outputs can be generated at the end of the simulation by setting the variable 'graphic_result' to 1. Note that Python Image Library (PIL) should be installed using the command below:
```
pip install pillow
```
As there is a limitation in drawing the shapes in Python, if the number of tasks is high, keep this feature disabled in the simulator.
<br/>
<br/>
## Benchmark
Two benchmarks are provided in the simulator (placed in the benchmark folder), including a DOT file (that contains the task ID and data dependencies of the tasks) and a JSON file (that contains the execution times for each task). Two JSON files are provided for each benchmark, where the task execution time are measured in the cases running with 4 and 8 threads. To use them in the simulator, simply rename one of the files to bench_json (where bench is the name of the benchmark) before the simulation process. Note that the execution times are measured using the Extrae [1] and Papi [2] tools, as well as the JSON files are generated using a script [3] and the Paraver toolset [4].
<br/>
<br/>
Any new benchmarks can be easily added to this set and applied in the simulator, following the structure of the existing DOT and JSON files.
<br/>
<br/>
## Execution
The simulation process runs using the following command:
```
python simulation.py
```
If the graph should be generated based on the benchmark, press 'y'; otherwise press 'n'.
<br/>
<br/>
## References
[1] Barcelona Supercomputing Center (BSC), "Extrae," December 2023. https://tools.bsc.es/extrae/
<br/>
[2] Innovative Computing Laboratory, University of Tennessee, "Performance Application Programming Interface, PAPI," April 2023. https://icl.utk.edu/papi/index.html/
<br/>
[3] Barcelona Supercomputing Center (BSC), "TDG instrumentation," December 2023. https://gitlab.bsc.es/ampere-sw/wp2/tdg-instrumentation-script/
<br/>
[4]	A. Munera, S. Royuela, G. Llort, E. Mercadal, F. Wartel, and E. Quiñones, "Experiences on the characterization of parallel applications in embedded systems with extrae/paraver," in Proc. of the 49th Int. Conference on Parallel Processing (ICPP '20), Edmonton, AB, Canada, pp. 1–11, August 17–20, 2020.
