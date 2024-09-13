# Operating System Lecture Notes (Lecture 1)

## **Introduction**

Hello, this is Lakshay, and today we are starting Lecture 1 of the Operating System (OS) series.  
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

An operating system is a piece of software that manages all the resources of a computer system (both hardware and software) and provides an environment in which the user can execute programs in a convenient and efficient manner.

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
