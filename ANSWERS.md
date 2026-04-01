# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:A process is a stand-alone program that runs independently and has its own memory and system resources. A process's memory and resources can be shared by several threads, each of which is a smaller execution unit. The primary distinction is that threads are lighter and faster than processes, which are more difficult to establish and maintain. Because the scheduler simulation runs numerous process objects inside a single Java application, threads were more appropriate for this task. This makes the simulation easier to use and more effective. Additionally, since all threads operate within the same program and can be directly managed using `Thread.start()`, `Thread.join()`, and shared data structures like the ready queue and the process map, communication and coordination are made simpler.**

[Write your answer here. Consider: What is a process? What is a thread? How do they differ in terms of memory, resources, creation overhead? Why are threads more suitable for this simulation?]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:In Round-Robin scheduling, a process does not instantly resume if it does not complete inside the allotted time period. Rather, in order to give other processes CPU time, the scheduler stops it, retains its remaining time, and puts it back at the end of the ready queue. Because lengthy programs are unable to monopolize the CPU, this behavior enhances fairness. This was evident in my result with P1, which used the entire 4000 ms quantum while still having 1439 ms left. P1 then returned to the ready queue to await another turn after yielding the CPU.**

[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

Example from my output:
```
? P1 executing quantum [4000ms]
  ? Quantum progress: [███████████████] 100%
  ? P1 completed quantum 4000ms │ Overall progress: [██████████████░░░░░░] 73%
     Remaining time: 1439ms
  ? P1 yields CPU for context switch

  ? P1 (Priority: 2) added to ready queue │ Burst time: 5439ms
[Paste a relevant snippet from your program output here showing a process being re-queued]
```

**Explanation of example:This output demonstrates that P1 failed to complete its initial execution round. The scheduler took it from the CPU and re-queued it after allowing it to run for precisely one quantum and determining that it still had 1439 ms remaining. Later on in the output, P1 executed quantum [1439ms] once more before finishing. Unfinished processes go back to the queue and wait for another opportunity, which is the primary Round-Robin behavior.**
[Explain what's happening in the output snippet you pasted]

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:In this simulation, P1 progresses through the thread lifespan in a logical order. Initially, the software uses `new Thread(process)` to construct a thread for P1 inside `addProcessToQueue()`. At that point, the thread is in the **New** state. The thread becomes **Runnable**, indicating that the JVM is prepared to execute it, when the scheduler chooses P1 and invokes `currentThread.start()`. When the `run()` procedure starts and the output displays `P1 executing quantum [4000ms]` it then enters the **Running** state. The code simulates time passing during execution by using `Thread.sleep(stepTime)`, which causes the thread to enter a timed waiting state while resting in between progress updates. Ultimately, the thread becomes **Terminated** once the assigned execution for that instance of the thread has concluded.**

[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

1. **New**:P1 is in the New state when the thread object is first created with `new Thread(process)` before it starts running. [When is P1 in New state?]

2. **Runnable**:P1 becomes Runnable when the scheduler removes it from the ready queue and calls `currentThread.start()`.
 [When does P1 become Runnable?]

3. **Running**:P1 is Running when the `run()` method is actually executing. In my output, this appears as:
```text
  ? P1 executing quantum [4000ms] [When is P1 Running?]

4. **Waiting**:P1 enters a waiting-like timed state during the Thread.sleep(stepTime) calls inside the run() method. This is how the simulation represents CPU execution progress over time before printing:
 ? Quantum progress: [███████████████] 100% [When/why would P1 be Waiting?]

5. **Terminated**:
P1 becomes Terminated when that thread finishes its run() method for the current round. In my output, after its second turn, P1 finishes completely:
  ? P1 executing quantum [1439ms]
  ? Quantum progress: [███████████████] 100%
  ? P1 completed quantum 1439ms │ Overall progress: [████████████████████] 100%
     Remaining time: 0ms
  ? P1 finished execution!
This indicates that P1's final thread instance has finished executing and won't do so again.
 [When is P1 Terminated?]

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1:Web Server Request Handling [Name of application/scenario]

A description:
Many client requests can be handled concurrently by a web server, and each request can be handled by a thread. A Round-Robin-style scheduling concept is helpful if the server must distribute CPU time equitably among numerous active requests.

Why Round-Robin is effective in this situation:
Because no single request may hold the CPU for an extended period of time, Round-Robin enhances fairness. Additionally, it enhances responsiveness, particularly when numerous users are connected simultaneously. This is comparable to my software, in which each process receives one quantum and, if it still requires more time, returns to the queue.

### Example 2:Multiplayer Game Server [Name of application/scenario]

A description:
Multiple threads may be used by a multiplayer game server to handle numerous player updates, physics computations, and communication chores. Rather of having a single task run over an extended period of time, these processes frequently require periodic short CPU access.

Why Round-Robin is effective in this situation:
Round-Robin is effective because it provides regular and consistent CPU access to many jobs. This lessens the possibility that one demanding task will cause all others to be delayed and keeps the system responsive. The similar concept can be seen in my scheduler simulation, where each process is given a set amount of time and, if it is not finished, waits for its next turn.

## Summary

**Key concepts I understood through these questions:**
1. the actual distinction between processes and threads in terms of execution overhead and memory sharing.
2. How Round-Robin scheduling maintains fairness by requeuing incomplete tasks.
3. The appearance of thread lifecycle phases via start(), sleep(), join(), and completion in actual Java code.

**Concepts I need to study more:**
1. a more thorough explanation of the differences between blocked, timed, and waiting thread statuses.
2.more sophisticated CPU scheduling techniques, like multilevel feedback queues and priority scheduling.
 
