# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer:This assignment taught me that multithreading involves careful control over the execution of several tasks in addition to running them simultaneously. I began utilizing `Thread.start()` after comprehending how a thread is created from a `Runnable` object. Additionally, I discovered that the scheduler needs to correctly coordinate threads, which is why in this simulation, it was crucial to use `Thread.join()` to wait until one quantum had completed before proceeding to the next process. Another significant thing I discovered is that CPU burst time may be represented by simulating thread execution using `Thread.sleep()`. Additionally, I observed how a single logical process can be scheduled more than once by starting a new thread for every turn in the ready queue. I was able to make the connection between theoretical thread statuses and actual Java code thanks to this assignment. In general, I now have a better understanding of multithreading as an operating system concept and as a programming tool.**

[Write your answer here. Discuss specific concepts like thread creation, thread states, how threads execute concurrently, what surprised you, etc.]

---

## Question 2: What was the most challenging part of this assignment?

**Your Answer:Understanding how to change the starter code without altering its original behavior was the most difficult aspect of this assignment. The broad Round-Robin concept was initially simple to grasp, but determining the precise locations of each new feature in the code proved to be more difficult. For instance, the waiting time feature necessitated meticulous monitoring of a process's entry into the ready queue and its commencement. The waiting time values would be off if this were put in the improper fashion. Maintaining the output's readability and clarity after adding priority, context changes, and the final waiting time summary presented another difficulty.I had to understand how changes are transferred from Visual Studio Code to GitHub, which made Git and commits difficult at first. Ultimately, comprehending the simulation's entire execution cycle proved to be more challenging than writing a single line of code.**

[Describe the specific challenge. Was it understanding the code? Implementing a feature? Using Git? Explain what made it difficult and how it relates to the course concepts.]

---

## Question 3: How did you overcome the challenges you faced?

**Your Answer:Instead of attempting to make all the changes at once, I overcome the obstacles by working incrementally. In order to comprehend the current scheduling behavior, I first executed the original code and closely examined the output. After that, I tested the application after adding each feature one at a time. This made it easier for me to pinpoint issues and determine which change was responsible for a particular problem.Additionally, I used the program's output as feedback, particularly when determining if a process was properly requeued or whether the final statistics showed up where they should have. I concentrated on figuring out the precise times when a process joins the queue and begins to run in order to track waiting times. After testing, I also fixed minor formatting errors to make my job better. This methodical approach decreased confusion and made the assignment easier to handle.**

[Describe your problem-solving approach. Did you read documentation? Ask for help? Debug systematically? What resources did you use? What strategies worked?]

---

## Question 4: How can you apply multithreading concepts in real-world applications?

**Your Answer:Many real-world applications that require multiple tasks to be completed simultaneously make use of multithreading ideas. To load sites, provide the user interface, and handle network requests without freezing the screen, for instance, a web browser requires many threads. Threads can be used concurrently for background computations, audio, user input, and rendering in a game. Threads in servers may manage numerous client requests at once, which enhances resource efficiency and responsiveness. Additionally, mobile applications use background threads to analyze files or download data while maintaining responsiveness on the main interface. I now have a better understanding of how these systems distribute CPU time across jobs rather than letting one activity take up all available time thanks to this assignment.It also demonstrated to me the value of coordination and fairness in addition to speed.**

[Give specific examples from real applications you use (web browsers, games, mobile apps, etc.). Explain why threads are useful in those scenarios. Connect to what you learned in this assignment.]

---

## Additional Reflections (Optional)

### What would you like to learn more about?

[Any topics related to threading, concurrency, or operating systems that you're curious about?]

---I'm interested in learning more about concurrent issues including starvation, deadlocks, and race situations as well as thread synchronization. Beyond just using Round-Robin, I also want to research how actual operating systems execute scheduling decisions. I also want to investigate the differences between simulation code like this assignment and multithreading on multi-core CPUs. These subjects, in my opinion, will enable me to advance from fundamental comprehension to more profound practical knowledge.

### How confident do you feel about multithreading concepts now?
in the middle.
Because I now comprehend thread formation, execution flow, and how scheduling behavior may be expressed in Java code, I feel more confident than I did before. I am able to describe what occurs during program execution by tracking a thread's lifespan. Additionally, I am aware of how Round-Robin scheduling ensures fairness and the significance of `sleep()`, `start()`, and `join()`. I still need to practice debugging multi-threaded applications in larger systems and advanced concurrency subjects, though.
[Rate yourself and explain: Beginner / Intermediate / Confident]

[Explain your rating - what do you understand well? What needs more practice?]

---

### Feedback on the assignment
This assignment was beneficial since it made a connection between Java code and operating systems theory. The fact that it began with a pre-built simulation and then requested particular feature enhancements was appealing to me because it made the learning process more organized. The job felt more realistic and professional because of the necessary documentation and GitHub commits. Seeing the scheduler behavior directly in the terminal output was the most helpful feature. The task was difficult but fair, in my opinion, especially since it called for both coding and explanation. All things considered, it was a useful method for honing technical comprehension and software development techniques.
[Any comments about the assignment? Was it helpful? Too easy/hard? Suggestions for improvement?]
