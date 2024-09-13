# Operating System Lecture Notes (Lecture 1)

## **Introduction**
 
We will begin with the basics of what an OS is, why it is necessary, and why it exists.

---

## **Why is an OS Necessary?**

### **What Happens if an OS Doesn't Exist?**

Imagine using a mobile or tablet to run an app like TikTok. To run it, you need resources such as:
- CPU
- Memory
- GPU
- Disk

Without an OS, when TikTok is launched, it will take control of these resources directly, leaving nothing for other apps. If you then try to open another app like PUBG, it won’t have access to resources and will enter a hang state.

---

### **Resource Management by OS**

- OS manages resource allocation to ensure multiple apps can run simultaneously without hogging all resources.
- For example, the OS allocates:
  - 5% CPU, 10% memory, and 12% GPU to TikTok.
  - 50% CPU, 50% memory, and 60% GPU to PUBG.
  
This efficient allocation of resources ensures smooth running of both apps. This process is called **resource management**, one of the core functions of an OS.

---

## **OS as an Interface**

- The OS acts as an interface between the user apps and hardware resources.
  
### **Analogy**:

- You, the user, are like a person withdrawing money from the bank.
- The bank teller acts as an interface between you and the treasury (the resource).
- In OS terms:
  - The user app is you.
  - OS is the interface (bank teller).
  - Hardware resources like CPU and memory are the treasury.

OS ensures that the app doesn’t interact directly with the hardware but goes through it to manage everything efficiently.

---

## **Problems Without an OS**

### **Memory Management Issues**: 
- Without an OS, developers would have to write memory management code themselves for every app, leading to bulky apps.
  - For example, TikTok and PUBG would both require redundant code for resource management, making each app significantly larger (from 50MB to 700-800MB).
  
### **DRY Principle Violation**: 
- Writing the same resource management code in every app violates the **"Don’t Repeat Yourself" (DRY)** principle. The OS solves this by managing memory, scheduling, and processes on behalf of the apps.

---

## **Functions of an OS**

1. **Resource Management**:
   - Manages how much CPU, memory, GPU, etc., are allocated to each app.
2. **Interface**:
   - Acts as an interface between the user apps and hardware resources.
3. **Abstraction**:
   - OS handles the complex hardware interaction behind the scenes, providing developers with a simple way to access resources without worrying about how they’re allocated.
4. **Isolation and Protection**:
   - Provides memory isolation and protection between different apps.
   - For example, if TikTok and PUBG are running simultaneously, OS ensures TikTok doesn’t interfere with PUBG’s memory, preventing security violations like one app overwriting the data of another.

---

## **Security Risks Without OS**

Without an OS, there is no **isolation** between apps. One app could potentially overwrite the memory of another, leading to problems like:
- TikTok could overwrite PUBG’s memory, causing PUBG to show incorrect data (e.g., reducing the player's health to 0%).
- OS provides **memory protection** by keeping each app’s memory separate.

---

## **Summary of Problems Without an OS**

1. **Resource Exploitation**: Apps would take over all available resources.
2. **Redundant Memory Management Code**: Developers would need to write resource management code for each app, leading to bulkier and more complex applications.
3. **Lack of Memory Protection**: No isolation between apps, risking security violations.

---

## **Formal Definition of an OS**

An operating system is a piece of software that manages all the resources of a computer system (both hardware and software) and provides an environment in which the user can execute programs and run applications in a convenient and efficient manner without any conflicts .

### **Key Roles of OS**:
- Hides hardware complexity.
- Acts as a **resource manager** by allocating CPU, memory, and other resources efficiently.
- Provides a secure and isolated environment for app execution.

---

## **Summarized Lecture (Key Points)**

1. **Resource Management**: The OS manages resources like CPU, memory, GPU, and disk, ensuring no single app dominates all resources, allowing multiple apps to run simultaneously.
  
2. **Interface**: The OS acts as a bridge between apps and hardware, preventing direct interaction and managing hardware requests efficiently.
  
3. **Abstraction**: Developers only need to focus on writing application logic, while the OS handles complex hardware operations like memory management and scheduling.
  
4. **Memory Isolation and Protection**: The OS separates the memory used by different apps, preventing one app from interfering with or accessing the memory of another app, enhancing security.
  
5. **DRY Principle**: Without an OS, developers would need to repeat memory and resource management code for every app, making them bulky and complex. The OS avoids this by centralizing resource management.
  
6. **Prevents Resource Exploitation**: The OS ensures that resources are shared fairly among apps, preventing any single app from taking over the entire system’s resources.
  
7. **Execution Environment**: The OS creates a convenient and efficient environment for developers to run their programs without worrying about low-level hardware interactions.

---

## **Simple Definitions of an Operating System**

1. **Definition 1**: An OS is software that manages all the resources of a computer, such as memory, CPU, and storage, and makes sure different apps can run smoothly without conflict.
  
2. **Definition 2**: The OS is like a manager for your computer, handling all the behind-the-scenes work so that you can run apps without worrying about how the computer’s hardware works.
  
3. **Definition 3**: An operating system helps apps communicate with the computer’s hardware (like the CPU, memory, etc.) by managing how resources are shared, keeping things organized, and ensuring security.
  
4. **Definition 4**: OS acts as a middleman between the user’s apps and the computer hardware, providing a safe and efficient way for apps to use the computer’s resources.


# OS Lecture 2: Types of Operating Systems

Hello ji, how are you all? This is Lakshay.  
Welcome to the **Code Help** channel. Today, we will discuss **Lecture 2** of our OS series.

We will explore some interesting topics:

1. Types of Operating Systems (OS) and how many types there are?
2. How are they built?
3. Goals that were considered while designing them.

## Goals of Any Operating System (OS)

### 1. Maximum CPU Utilization
The primary function of an OS is to run processes efficiently. You want multiple processes to run without keeping the CPU idle.

- Example: You have processes P1, P2, and P3. If P1 is performing I/O operations, the OS should allow P2 or P3 to execute instead of keeping the CPU idle.

This ensures **maximum CPU utilization**, which is the first goal of an OS.

### 2. No Process Starvation
Process starvation occurs when a process doesn’t get CPU time because another process hogs it.

- Example: Suppose P1 is a long process with an infinite loop. It would prevent P2 and P3 from executing, which is undesirable. All processes should get their chance to execute.

This brings us to our second goal: **No process starvation**.

### 3. High Priority Jobs Execution
The OS must be capable of handling high-priority jobs.

- Example: Consider processes P1, P2, and P3 running, and suddenly a high-priority job P4 (e.g., an antivirus scan) arrives. The OS should ensure that P4 gets executed immediately.

Thus, **high-priority job execution** is our third goal.

---

This video is sponsored by **Crio**, the world's leading project-driven platform. If you're targeting a good job and want to master development, Crio is for you.

Crio offers various programs like **Full Stack Development** and **Backend Development** with internship-level projects. At the end of each program, you'll have a project-rich resume. They also offer a **Fellowship Program** with guaranteed placement in a product-based company.

If you're interested, check out the link in the description for a 1-week trial and get an **assured scholarship** and **maximum discount** using the coupon code displayed on the screen.

---

## Types of Operating Systems (OS)

### 1. Single Process OS
- **Description**: A simple OS where only one job is executed at a time.
- **Example**: MS-DOS.
- **Limitations**:
    - **CPU Utilization**: Poor, as only one job executes at a time. If P1 waits for I/O, other jobs like P2 and P3 remain idle.
    - **Process Starvation**: Yes, as other jobs wait if P1 is a long-running process.
    - **High Priority Job Execution**: Not supported, since only one job can run at a time.

### 2. Batch Processing OS
- **Description**: Jobs are grouped into batches and submitted for execution.
- **Example**: Punch card systems.
- **Limitations**:
    - **CPU Utilization**: Still poor, as jobs are processed sequentially within batches.
    - **Process and Batch Starvation**: Yes, if one batch or job takes too long, others will starve.
    - **High Priority Job Execution**: No, as batches are executed in order without interruption.

### 3. Multi-programming OS
- **Description**: Multiple jobs reside in memory, and whenever a job goes to I/O, the CPU executes another job.
- **Advantages**:
    - **CPU Utilization**: Improved, as the CPU doesn’t remain idle during I/O operations.
    - **Process Starvation**: Reduced, since multiple jobs get chances to execute.
    - **High Priority Job Execution**: Supported through **context switching**.

#### Context Switching Example:
Consider studying Physics and Chemistry for exams. You close your Physics books, save your progress, and switch to Chemistry. Similarly, the OS saves the current process state (via the **Process Control Block (PCB)**) and switches to another process.

### 4. Multi-tasking OS
- **Description**: An enhancement of multi-programming with **time-sharing**. Each process is given a small time slice (quantum) for execution.
- **Advantages**:
    - **CPU Utilization**: High, as the CPU continuously switches between jobs.
    - **Process Starvation**: Less, as each process gets equal time slices.
    - **High Priority Job Execution**: Yes, a high-priority job can interrupt others via **software interrupts**.

### 5. Multi-processing OS
- **Description**: An OS with multiple CPUs.
- **Advantages**:
    - **CPU Utilization**: Very high, as multiple CPUs execute jobs simultaneously.
    - **Reliability**: Increased, as failure of one CPU doesn’t halt the system.
    - **High Priority Job Execution**: Handled effectively across multiple CPUs.

### 6. Distributed OS
- **Description**: A loosely coupled system where multiple CPUs and memories are connected over a network.
- **Advantages**:
    - Jobs are distributed across different systems.
    - Examples include systems like **LeetCode**, where multiple jobs are executed on different systems connected over the internet.

### 7. Real-Time Operating System (RTOS)
- **Description**: An OS where tasks are executed in real time with minimal delay.
- **Applications**: Used in critical systems like **Air Traffic Control (ATC)**, **nuclear plants**, and **industrial control systems**.

---

These are the different types of Operating Systems.

