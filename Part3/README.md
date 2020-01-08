# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to your groups repository to complete the task.

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
 > Parallelism means we are literally executing multiple things at once on multiple cpu cores.
 
 Concurrency is process of switching single cpus time betwen processes/thread to make an illusion of paralelism.
 
 ### Why have machines become increasingly multicore in the past decade?
 > CPU manufactures don't know how to meaningfully increase frequency of the CPU.
 
 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 > Any problems that are too big to be finished on single core(ones that we have right know) in acceptable time. (Weather prediction, Fluid simulations ...)
 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 > Usually harder, with some exceptions.
 
 ### What are the differences between processes, threads, green threads, and coroutines?
 > A process is a program that has been loaded into memory along with all the resources it needs to operate.
 
 A thread is the unit of execution within a process.
 
 A green thread is thread that is scheduled by a runtime library or virtual machine instead of natively by the underlying operating system.
 
 Coroutine is like a thread but the decisions on how/when/... to switch betwen coroutines is up to the programmer not the os.
 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 > The pthread_create() function starts a new thread.
 
 threading.Thread() creates a new thread.
 
 go starts a new green thread.
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > GIL allows only one thread per process to be executed at a time.
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > We replace thread-based concurrency with process-based paralelism.
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 > GOMAXPROCS sets the maximum number of cpus that can be executing simultaneously.
