**Copyright @ Anshuman Kundu**

# Node Js Interview Questions with proper explanation and understanding
*by Anshuman Kundu*


### 1. What is Node.js?
1. Node.js is neither a language nor a framework.
2. It is a runtime environment to run javascript codes on the server side.
3. Browser executes javascript on the client side and Node executes javascript on the server side.
4. V8 is a javascript engine which helps executing javascript.

### 2. What is the difference between a Framework and a Runtime Environment?
1. A runtime environment provides a platform for code execution and provides services like memory management and I/O operations.
2. A framework provides a set of tools and libraries with best practices to make development easy.

### 3. What is Express.js?
1. It is a framework built on top of Node.js.
2. It simplifies the backend process of creating web applications like API creation, routing, middlewares, etc.

### 4. Explain the request response practical procedure.
1. When a user requests something over the internet in the browser, it goes to the server.
2. The server running on a Node environment executes or communicates with the database or some other listed APIs and returns the reposnse back in the form of HTML, CSS and JS.

### 5. What are some main features of Node.js?
1. Asynchronous
2. NPM (node package manager)
3. Single Threaded
4. Event driven
5. Cross Platform (can run on any OS)

### 6. What is Synchronous Programming and Asynchronous Programming?
1. Let's suppose in the server side we have 5 independent tasks to be performed.
2. In sync programming, tasks will be exceuted one by one and while one task is being executed, it will act as a blocker to all other tasks.
3. Sync Programming can make the response and execution time very high and slow.
4. Async Programming on the other hand will initiate all the tasks together and the task execution will be done simultaneously (all running in parallel) without waiting for the other tasks to be completed unlike sync programming.
5. Async Programming makes the response and execution time very low and fast.

### 7. What is Single-Threaded Programming and Multi-Threaded Programming?
1. When a request is sent to the API (server) and let's assume that in order to provide the response back, the server has to perform 5 independent tasks.
2. A thread is created to initiate tasks and when every task is completed, that thread is responsible for communicating to the server that the operations are done.
3. This thread goes to each task for task initiation.
4. If this thread waits for the task to be completed before moving on to another task for task initiation then it is called **Single-Threaded Synchronous Programming**.
5. If this thread does not wait for the task to get it done and moves to other tasks for initiation then it is called **Single-Threaded ASynchronous Programming**.
6. When a thread is created initially, it goes to task A for initiation and after initiation it sees another task B just in sequence with A then it breaks down the thread and creates another thread to go start task initiation for B and so on.... This is called **Multi-Threaded Programming**. It is always Asynchronous.

### 8. Why is Node.js termed as 'Event Driven'?
1. Events: Anything happening in a program is an event.
2. Event Emitters: Something happened in a program is caused by let us say X. This X is Event Emitter.
3. Event Queue: All the occurring events are put in a queue.
4. Event Loop: Picks up the events from the Event Queue in FIFO basis and takes it to the corresponding Event Handlers (Listeners) to perform some action.
5. Therefore all the operations in Node.js are based on what actually happeded which is nothing but an Event, that's why its called **Event Driven**.

### 9. When to use Node.js for Backend development?
1. Building real time applications.
2. Building scalable and lightweight RESTful APIs.
3. Building microservice based architecture.

### 10. When not to use Node.js for Backend development?
1. Building applications with heavy computations and CPU intensive tasks: Because Node.js is single-threaded and for heavy computations, multi-threaded programming is prefered for top notch performance.

### 11. What is NPM and what is role of node_modules folder?
1. NPM - Node package manager : It is used to manage all the dependencies required for a Node project.
2. node_modules folder stores the raw codes of all the dependencies for the Node project.
   
### 12. What is the role of package.json?
1. package.json stores the complete project metadata i.e every information about the node project including project name, author, licenses, dependencies name, etc.

### 13. What is the difference between a module and a function?
1. A module is responsible for a specific functionality which can be made up of multiple functions integrated.
2. A function is merely a set of instructions to be performed.
3. There are two ways to export them for reusablitiy: 1. module.exports.func1 = func1 or export func1;

### 14. What are the types of modules?
1. Built in Modules: Comes with the Node project.
2. Local Modules: Users make to implement some specific functionality.
3. Third party modules: Needs to be installed as per the requirement.

### 15. What is the role of **fs** module?
1. It is used to interact with the file system.
2. It can help in reading, writing, deleting, etc a file in the file system.

### 16. What is the role of **path** module?
1. It is used to manipulate paths.
2. It has methods like join which can help in formatting, parsing paths in your node project.
   
### 17. What is the role of **os** module?
1. It is used to interact with the Operating system.

### 18. What is the role of **events** module?
1. It is used to handle the occurring events.

### 19. What is the role of **http** module?
1. It is used to interact with the server ports and send back response to the client.
2. It has a createServer() function which helps create a server which can listen on a specific port.

### 20. What is the difference between a function and an event?
1. Event: Anything happening in a program is termed as an event.
2. Function: It can be used to perform some action when an event is caught (Event handlers are functions only).



**Copyright @ Anshuman Kundu**