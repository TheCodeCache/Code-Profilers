# Python Profilers
Experiments with **Cpu** profiling and __memory__ profiling

There are two ways to inject code to watch a program run: tracing and profiling. 
	They are similar, but intended for different purposes and so have different constraints. 
		The easiest, but least efficient, way to monitor a program is through a trace hook, 
		which can be used for writing a debugger, code coverage monitoring, or many other purposes.

Profiling an application is a dynamic code analysis where we investigate the behavior of the given code or program using the collected data while the code runs. 
It helps to identify different sections of code that we must optimize 
	to increase the application performance, its speed, latency and decrease its memory footprint as well as resource consumption..

PFB the techniques behind Profiling:
- Instrumented approach
- Sampling approach
- Event-Based
- Statistical
- Simulation

