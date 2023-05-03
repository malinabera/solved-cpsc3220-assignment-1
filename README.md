Download Link: https://assignmentchef.com/product/solved-cpsc3220-assignment-1
<br>
<strong>Task at Hand</strong>

<ol>

 <li>In this assignment you will write a C program named <em>c</em> that will have a total of 2 processes: a parent, and a child.</li>

 <li>Child process will be given its own routine to execute (file named child_function.c) and will be passed an integer that will come from the command line as the first argument. Child process will increment that integer by 10 and print the result to the standard output (screen). This can be accomplished by passing the name of the executable file (along with that integer) to the execl(…) call. Printing out the resulting value will be done inside that function.</li>

 <li>Parent process will create two threads, call a function named thread_func and pass two integers (second and third CLA) to the corresponding threads. Inside that function this integer will be multiplied by 10 and results will be returned to the parent via calls to thread_exit/thread_join. The parent will then print all his information (pids, data values) from the main (NOT from the thread function). Please study the examples in Files/code examples/processes and threads folder.</li>

 <li>When you execute your program, your output should be exactly as the one shown below, with the exception of the process/thread ids – those will be different from the ones shown. Also please keep in mind that different tasks may be scheduled to run at a different time than in the example below, so your output may appear in a different order.</li>

</ol>

<strong>Hints (hopefully helpful)</strong>

<ol>

 <li>Work incrementally, save/compile/run often. First get one of the processes to work, then the other one.</li>

 <li>Study the execl code example with count.c that does almost exactly what your child needs to do. The first CLA is passed to the child function via the execl call.</li>

 <li>Do not forget that the parent process needs to wait for the child to finish executing.</li>

 <li>Declare a void * variable to hold integers you will pass to threads, which will make it easier to deal with pointers.</li>

 <li>Use a lot of debugging statements to see what values you are getting at different points of execution. This will be especially helpful when you are dealing with returning and casting pointers.</li>

 <li>Do not forget to include header libraries for threads and processes and use -pthread to compile file that handles threads.</li>

 <li>Have a plan A and plan B, do not wait till the last moment to start this assignment, as unforeseen events happen at the least convenient time.</li>

</ol>

<strong>To compile:</strong>

Compile your child_function code and then main file and rename their executables to something other than the generic a.out. You are nor required to have/submit a makefile.

gcc child_function.c -o child_function gcc asg1.c -o asg1 -pthread

<strong>To run:</strong>

./asg1 17 11 22

(Note: 17 will go to the child via execl call and 11 and 22 to the threads in thread_create)

<strong>Output:  </strong>(your pids will be different than the ones shown)

Child process: PID 39809 and PPID 39808, Initial value: 17, Result:  27

Parent process: PID 39808 and PPID 39676

Thread 324723463634, Initial value: 11,  Result is: 110

Thread 324723463642,  Initial value: 22,  Result is: 220