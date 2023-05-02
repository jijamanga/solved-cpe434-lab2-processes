Download Link: https://assignmentchef.com/product/solved-cpe434-lab2-processes
<br>



A process is an instance of a program. The new process is created by issuing a fork system call. Each process has its own area of memory, protected against modification by other processes. The ​<strong>fork ​</strong>system call creates a copy of a process that was executing. The process that executed the fork is called the ​<strong>parent ​</strong>process and the new process is called the ​<strong>child ​</strong>process. . The only difference in the returns from the fork system call is that the return value in the parent process is the process id of the newly created child process, while the return value in the child process is zero. If the fork is not successful, -1 is returned.

A process terminates by calling the ​<strong>exit ​</strong>system call. This system call never returns to the caller. When exit is called, an integer exit status is passed by the process to the kernel.

<h1>Exercises</h1>

<ol>

 <li>Write a program that does the following in the order given below:

  <ol>

   <li>declare and initialize a variable named ​<em>val ​</em>(initialize to 0)</li>

   <li>call fork system call</li>

   <li>in the child process, add 2 to the value of ​<em>val​</em>, and print it on the console screen along with the pid of the child in the same statement.</li>

   <li>in the parent process, add 5 to the value of ​<em>val​</em>, and print it on the console screen along with the pid of the parent process in the same statement.</li>

   <li>What can you conclude about the values of the variable ​<em>val​</em>?</li>

  </ol></li>

 <li>Write a program, which creates a new process ​<em>child1​</em>. The parent process should print its id and wait for the termination of the ​<em>child1 ​</em> The ​<em>child1 ​</em>process should call a function that subtracts two numbers passed as arguments, print the result on the console screen along with the pid of the process that is printing. It should then create a new child ​<em>child2 </em>process that adds two numbers. The control should then come back to the first child process ​<em>child1 ​</em>that now should multiply two numbers and then terminate. The waiting parent process should now resume and terminate the program .</li>

 <li>Write a program, which creates n child processes and prints their process id. The n must be an even number and passed as argument, otherwise a message indicates that the number is odd and terminates the program. Please make sure that your implementation has one parent process and n-1 child processes.</li>

 <li>Write a C program that demonstrates the concept of following:

  <ol>

   <li>Orphan Process</li>

   <li>Zombie Process</li>

   <li>Sleeping Beauty Process</li>

   <li>Verify that you actually achieved all the three states mentioned above by using the terminal. Put a screenshot of the process table in your report.</li>

  </ol></li>

</ol>

<strong> </strong>

<h1>Topics for Theory</h1>

Define and discuss the following: process, states of processes, orphan process, and zombie process. Additionally, write a paragraph on each of the functions mentioned in the hint (fork(), exit(), and wait()).

<h2>Hint</h2>

<strong>int fork() ​</strong>: function either returns 0 for child process or the process id if it is parent.

<strong>exit(status)​</strong>: when exit is called, an integer exit status is passed by the process to the kernel. (used usually by the child process to terminate and return it’s status to the parent process). <strong>int wait(int *status)​</strong>: a process can wait for one of its child processes to finish by executing the wait system call. The value returned by wait is the process id of the child process that terminated . If there are more than one child processes, then the wait function returns after any one child is terminated and the value returned is the pid of the child.