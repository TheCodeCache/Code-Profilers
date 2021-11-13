# Python Profilers  
Experiments with **Cpu** profiling and __memory__ profiling  

When we have a performance problem, or we just want our code to run faster, we reach for profiler to help us identify problems and hopefully fix them.  

There are two ways to inject code to watch a program run: tracing and profiling.  
  They are similar, but intended for different purposes and so have different constraints.   
    The easiest, but least efficient, way to monitor a program is through a trace hook,  
      which can be used for writing a debugger, code coverage monitoring, or many other purposes.  

Profiling an application is a dynamic code analysis  
  where we investigate the behavior of the given code or program using the collected data while the code runs.   
It helps to identify different sections of code that we must optimize  
  to increase the application performance, its speed, latency and decrease its memory footprint as well as resource consumption..  

PFB the techniques behind Profiling:  
- Instrumented approach  
- Sampling approach  
- Event-Based  
- Statistical  
- Simulation  

The first 2 techniques are the most commonly used to develop profilers.  

Following is the list of most commonly used profilers in python:  
1. pprofiler_stat
2. py_spy
3. pyinstrument
4. cProfile
5. yappi_wallclock
6. yappi_cpu
7. line_profiler
8. Profile
9. pprofile_det
10. memory_profiler
11. Scalene

Normalized Execution Time:  
  which means: we took the time running the profiler, and divide it by how long it took to run the program without the profiling.  
  that means, the best case would be 1.0x meaning no overhead.  
 
       ![profiler_1](https://user-images.githubusercontent.com/26399543/141614410-dd0b2be5-8d52-4ba6-9c15-ddf186a13c0c.png)  

All the profilers listed in the image above except `memory-profiler`. profiles only `Cpu`,  
  whereas `memory-profiler` profiles only `memory`  

A profiler profiles either by `function` or by `lines`.  
  If there are small-2 functions, then it is good to use to function-level profilers  
    and to profile any given function, we can annonate that function with `@profile` annotation  
  When we have a function with large number of lines, then it makes sense to use line-level profilers  

`Scalene` simultaneously performs line-level as well as function-level profiling.  

       ![image](https://user-images.githubusercontent.com/26399543/141615605-f18ad33a-1e0b-4899-a3f5-4151f7f65564.png)  

In the image above, thte description of the attributes are as follows:  
- Lines or Functions : whether the profilers profiles `lines` or `functions`  
- Unmodified code: whether it requires to modify the code before the profiler can profile it  
- Threads: whether a profiler can profile python user `threads`  
- Multiprocessing: whether a profiler can profile python user `processes`  

When it comes to memory profiling, `memory_profiler` has almost 300 times overhead whereas `Scalene` only has 20 times overhead

```It turns out that `Scalene` stands out among all the profilers out there, when it comes to the ability to profile python code```  

Reference(s):  
1. https://www.youtube.com/watch?v=5iEf-_7mM1k&t=26s
2. https://github.com/plasma-umass/scalene#readme  
  
  
  
