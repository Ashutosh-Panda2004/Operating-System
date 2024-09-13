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

## Types of Operating Systems (OS)

### 1. Single Process OS
- **Description**: An operating system that allows only one process to execute at a time, leading to serial job processing.
- **Example**: MS-DOS.
- **Limitations**:
    - **CPU Utilization**: Inefficient, as only one process runs at a time. If the active process is waiting for I/O, the CPU remains idle.
    - **Process Starvation**: Can occur if one long-running process prevents other jobs from executing.
    - **High Priority Job Execution**: Not supported, as only one job can run at a time.

### 2. Batch Processing OS
- **Description**: Groups of jobs are collected and executed sequentially in batches.
- **Example**: Early punch card systems.
- **Limitations**:
    - **CPU Utilization**: Suboptimal, as jobs within batches are executed sequentially without overlap.
    - **Process and Batch Starvation**: A lengthy job or batch can delay the execution of others, causing starvation.
    - **High Priority Job Execution**: Not supported, as batch jobs are executed in a fixed order.

### 3. Multi-programming OS
- **Description**: Multiple jobs reside in memory simultaneously, and the OS switches between them to keep the CPU active.
- **Advantages**:
    - **CPU Utilization**: Improved, as the CPU continues executing other jobs while one is waiting for I/O.
    - **Process Starvation**: Reduced, as multiple jobs get execution opportunities.
    - **High Priority Job Execution**: Supported through **context switching**.

#### Context Switching Example:
Just like switching between study subjects by saving progress in one and moving to another, the OS saves the current process state using the **Process Control Block (PCB)** and switches to another process.

### 4. Multi-tasking OS
- **Description**: Builds on multi-programming by incorporating **time-sharing**, where each process receives a time slice for execution.
- **Advantages**:
    - **CPU Utilization**: High, due to constant switching between processes.
    - **Process Starvation**: Minimized, as each process receives an equal time slice.
    - **High Priority Job Execution**: Supported via **software interrupts**, allowing high-priority processes to preempt others.

### 5. Multi-processing OS
- **Description**: An OS designed to work with multiple CPUs.
- **Advantages**:
    - **CPU Utilization**: Maximized, with multiple CPUs handling different tasks concurrently.
    - **Reliability**: Enhanced, as system failure due to one CPU doesn’t affect others.
    - **High Priority Job Execution**: Effectively managed across multiple processors.

### 6. Distributed OS
- **Description**: A system where multiple CPUs, each with its own memory, are connected over a network to distribute tasks.
- **Advantages**:
    - Jobs can be distributed across different systems, improving scalability.
    - An example is **LeetCode**, where multiple jobs run on different machines over the internet.

### 7. Real-Time Operating System (RTOS)
- **Description**: An OS that ensures tasks are executed within a specific, minimal response time.
- **Applications**: Commonly used in critical applications like **Air Traffic Control (ATC)**, **nuclear plants**, and **industrial automation**.



---

These are the different types of Operating Systems.

