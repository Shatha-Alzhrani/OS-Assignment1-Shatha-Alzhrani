# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 - [March 29, 2026, 9:15 AM]
**What I did**: Run the starter code and set up the repository.

**Details**:
-The repository was opened in Visual Studio Code.
-Examined the project's files
-I changed the student ID in SchedulerSimulation.java to my real ID.
-To comprehend the ready queue behavior and output format, the original simulation was run.

**Challenges**: 
I wasn't quite at ease with Git at first, and I didn't understand the distinction between GitHub updates and local changes.

**Solution**: 
I worked slowly in Visual Studio Code, looked at the Source Control panel, and discovered that in order for changes to show up on GitHub, I need both a commit and a sync.

**Time spent**: 40 minutes .

---

### Entry 2 -[March 30, 2026, 4:00 PM]
**What I did**: I put Feature 1 (Process Priority) into practice.

**Details**:  
- The `Process` class now has a `priority` field.
-The constructor was updated to be given precedence.
-Random priorities ranging from 1 to 5 were generated in `main`.
-The ready queue message was changed to show the priority of each task.

**Challenges**:
The process name was missing and the text was repeated, therefore my first output formatting for the ready queue message was incorrect.

**Solution**: 
I carefully examined the print statement, corrected the formatting, and retested the output until every process showed up as `P1 (Priority: X) added to ready queue`.

**Time spent**: 55 minutes .

---

### Entry 3 - [March 31, 2026, 8:10 AM]
**What I did**: I put Feature 2 (Context Switch Counter) into practice.

**Details**: 
- In `SchedulerSimulation`, a static counter variable was added.
-Every time a new thread was chosen from the ready queue, the counter was increased.
-Near the simulation's conclusion, the total number of context switches was shown.
- Confirmed that the final result accurately displayed the total

**Challenges**:  
In order to reflect real scheduling shifts rather than arbitrary code execution steps, I had to determine where to increment the counter.

**Solution**:
Since the CPU starts processing the next scheduled process at that point, I put the increment right after polling the next thread from the queue.

**Time spent**: 35 minutes .

---

### Entry 4 - [March 31, 2026, 9:30 AM]
**What I did**: I put Feature 3 (Waiting Time Tracking) into practice.

**Details**:
- The `Process` class now has timing fields.
-Utilized the system to monitor queue entry time and overall waiting time, use currentTimeMillis()`.
-To store all processes for the final summary table, a list was added.
-The process summary with the process name, burst time, and waiting time was printed.

**Challenges**: 
Because waiting times depend on precise timing points, this was the most challenging element. I had to determine when a process joins the queue and begins to run.

**Solution**:
I added the elapsed time to `totalWaitingTime` at the beginning of `run()` after updating the process timing when it entered the ready queue. Realistic values were shown in the summary table following testing.

**Time spent**: 1 hour and 20 minutes .

---

### Entry 5 - [April 1, 2026, 6:00 PM]
**What I did**: Final testing, cleanup, and documentation.

**Details**: 
-Once all three features were finished, the entire program was run once more.
- Confirmed that priority, context switch count, and waiting time summary were included in the final output.
-Examined the code's comments to make sure every feature was properly documented.
- Made the markdown files for the development log, reflection, and responses.

**Challenges**: 
I wanted to ensure that all necessary assignment components adhered to the guidelines and that the final product was still readable.

**Solution**:
Before submitting, I arranged the final code and documentation, tested the simulation once more, and matched my findings with the assignment requirements.

**Time spent**: 50 minutes.

---

## Summary

**Total time spent on assignment**: 4 hours and 20 minutes were spent on the assignment in total.

**Most challenging part**: The most difficult aspect is correctly implementing the waiting time functionality without changing the original Round-Robin behavior.

**Most interesting learning**: The most fascinating thing I learned was how Java code and terminal output accurately reflect theoretical thread lifespan and CPU scheduling principles.

**What I would do differently next time**:  To save time during the final review, I would begin the documentation earlier and test each feature right away after coding it.
