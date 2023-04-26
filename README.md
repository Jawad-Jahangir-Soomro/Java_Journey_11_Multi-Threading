# Java Journey, 11: Multi Threading.

Repository #11 Multi-Threading is a collection of resources and examples that focus on the concept of multithreading in Java. It covers the basics of threads, Thread LifeCycle. The repository is designed for both beginners and experienced Java programmers looking to master the art of creating and managing threads in their applications.

## What is MultiTasking

Multitasking is the concurrent execution of two or more tasks or processes by a single CPU. In a multitasking system, the CPU switches between different processes or threads rapidly, giving the appearance of concurrent execution. This allows multiple tasks to be executed simultaneously, providing improved performance and responsiveness in computer systems. There are two main types of multitasking: process-based and thread-based. Process-based multitasking allows multiple processes to be executed simultaneously, while thread-based multitasking allows multiple threads within a single process to be executed concurrently.

## Types of MultiTasking

Multitasking refers to the ability of a computer system to perform multiple tasks simultaneously. There are two types of multitasking:

1- Process-based multitasking: In this type of multitasking, the operating system divides the available CPU time among the processes that are running. Each process gets a small slice of CPU time to execute its task, and the operating system rapidly switches between processes to give the illusion that they are running simultaneously.

Example: A computer running multiple programs such as a web browser, a media player, and a word processor simultaneously.

2- Thread-based multitasking: In this type of multitasking, a single process is divided into multiple threads, and each thread can execute a separate task. These threads share the same memory and resources and can communicate with each other to synchronize their activities.

Example: A program that creates a separate thread to download a file while the main thread continues to respond to user input.

## What is Thread

In computing, a thread is the smallest unit of execution within a process. It can be thought of as a lightweight subprocess or an independent path of execution within a program. A thread contains its own program counter, stack, and set of registers, and can share the memory and resources of the process to which it belongs.

In other words, a thread is a single sequence of execution that can run concurrently with other threads. It allows a program to perform multiple tasks at the same time, improving performance and resource utilization. Threads can be created and managed using programming languages like Java, which provides built-in support for multi-threading.

## Thread LifeCycle

The thread lifecycle represents the various states a thread goes through from its creation until its termination.

The thread lifecycle includes the following states:

1- New: When a thread is created, it is in the new state.

2- Runnable: When the start() method is invoked, the thread enters the runnable state. The thread is now eligible to be executed by the thread scheduler.

3- Running: When the thread scheduler selects the thread to execute, it enters the running state.

4- Waiting: A thread enters the waiting state when it is waiting for some condition to occur. For example, a thread can wait for a resource to become available or for a notification from another thread.

5- Timed waiting: A thread enters the timed waiting state when it is waiting for some condition to occur, but with a timeout specified.

6- Blocked: A thread enters the blocked state when it is waiting to acquire a lock on an object that is currently held by another thread.

7- Terminated: A thread enters the terminated state when its run() method completes execution or when an unhandled exception occurs.
During its lifecycle, a thread can transition from one state to another depending on various conditions.

For example, a thread in the running state can move to the blocked state if it tries to acquire a lock on an object that is already held by another thread. Similarly, a thread in the waiting state can move to the runnable state when the condition it is waiting for becomes true.

![thread-life-cycle](https://user-images.githubusercontent.com/123876118/234464770-969039f2-456b-4ad5-ab2c-4d3e70582f10.png)

## What is MultiThreading

Multithreading is a concept in which multiple threads of execution coexist within a single process. In other words, it allows an application to perform multiple tasks concurrently. Each thread of execution runs independently and can execute a different part of the code simultaneously.

For example, consider a web browser that downloads data from the internet while also displaying a GUI for the user to interact with. The download process can be run on a separate thread, while the GUI runs on the main thread. This way, the user can still interact with the GUI while the download process is ongoing.

Another example is a music player application that plays music in the background while allowing the user to perform other tasks such as browsing songs or using other apps. The music playing process can be run on a separate thread, allowing it to continue playing while the user performs other tasks on the main thread.

## Methods of MultiThreading

There are several methods of multithreading that can be used in Java. Some of them are:

1- Extending the Thread class: In this method, the class extends the Thread class and overrides the run() method to specify the behavior of the thread. For example:

```bash
class MyThread extends Thread {
  public void run() {
    // thread behavior
  }
}

MyThread thread = new MyThread();
thread.start();
```

2- Implementing the Runnable interface: In this method, the class implements the Runnable interface and provides an implementation for the run() method. For example:

```bash
class MyRunnable implements Runnable {
  public void run() {
    // thread behavior
  }
}

Thread thread = new Thread(new MyRunnable());
thread.start();
```

3- Using the Executor framework: This method provides a higher level of abstraction for managing threads. It allows for the creation of thread pools and the execution of tasks. For example:

```bash
Executor executor = Executors.newFixedThreadPool(10);
executor.execute(new MyRunnable());
```

These are just a few examples of the methods that can be used for multithreading in Java. The choice of method depends on the specific requirements of the program and the level of control needed over the threads.
