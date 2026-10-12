# Node.Js Interview Question & Answer
----

## Q. 1: What is Node.js?

***Answer:***  
Node.js is a JavaScript runtime environment that allows us to run JavaScript outside the browser. We use Node.js to develop the backend applications, build apis, handle requests and communicate with databases. It uses and event-driven, non-blocking I/O model, which helps it handle multiple request efficiently.   
::==> Node.js is neither a programming language nor a framework. It is a JavaScript runtime environment that allows us to run JavaScript outside the browser. We mainly use it to build backend applications and APIs.  

-----

### Follow up question:
 ### Explain the event-driven, non-blocking I/O model in Node.js.  
 
 ***Answer:***  
 Node.js follows an event-driven, non-blocking I/O model, which helps it handle multiple requests efficiently.  
First, I/O stands for Input/Output. It means operations where our application communicates with something outside the program, such as reading a file, fetching data from MongoDB, or calling an external API.  
Event-driven means Node.js works based on events. For example, when a database query is completed, an event or completion notification allows Node.js to process the result using a callback, Promise, or async/await.  
Non-blocking means Node.js does not have to wait for an I/O operation to finish before doing other work. While a database query is running, it can handle other incoming requests.  
For example, suppose two users send requests to our API. The first request needs data from MongoDB. While waiting for the database response, Node.js can start processing the second user's request instead of sitting idle.  
Once the database operation completes, Node.js processes the result and sends the response to the first user.  
This approach helps Node.js use its resources efficiently and handle many concurrent I/O requests without creating a separate thread for every request.

## Question 2: Why do we use Node.js for backend development?   

***Answer:***  
We use Node.js for backend development because it is fast, lightweight, and can handle multiple requests efficiently. It supports asynchronous and non-blocking operations, so it does not need to wait for one operation to finish before handling other tasks.  
Another advantage is that we can use JavaScript for both frontend and backend development. It is commonly used to build REST APIs, web applications, and real-time applications.  
*Example:* In an employee management system, we can use Node.js to create APIs for adding employees, getting employee details, updating employee information, and deleting employees.  

----
---- 

## Question 3: What are the main features of Node.js?  

***Answer:***  
Node.js has several important features that make it useful for backend development.  
1. `Asynchronous and Non-blocking I/O:` Node.js can handle other tasks while waiting for operations like database queries or file reading to finish.  
2. `Event-driven Architecture:` It responds to events, such as incoming requests or completed operations, and processes the results when they are ready.  
3. `Single-threaded: Node.js` uses a main JavaScript thread to execute JavaScript code, while handling many I/O operations without blocking that thread.  
4. `Fast Execution:` Node.js uses Google's V8 engine to execute JavaScript efficiently.  
5. `Scalable:` It can handle many concurrent requests, making it suitable for applications with multiple users.  
6. `NPM Support:` Node.js provides npm, which allows us to install and use packages that help us build applications faster.  
7. `Cross-platform:` Node.js applications can run on operating systems like Windows, Linux, and macOS.  
These features make Node.js a good choice for building backend applications, REST APIs, and real-time applications.  

----
----

## Question 4: How does Node.js work?  

***Answer:***  
Node.js uses the V8 engine to execute JavaScript code and follows an event-driven, non-blocking architecture.  
When a request comes to the server, Node.js executes the code using its main JavaScript thread. If the request involves an I/O operation, such as fetching data from MongoDB or reading a file, Node.js can start that operation without blocking other work.  
The Event Loop helps Node.js manage asynchronous operations and process their results when they are ready. Meanwhile, Node.js can handle other incoming requests.  
*For example,* when a user requests employee details, Node.js starts a database query. While MongoDB processes the query, Node.js can handle another user's request. Once the result is ready, Node.js processes it and sends the response to the first user.  
This is how Node.js handles multiple requests efficiently without needing a separate JavaScript thread for every request.  

-----
-----

## Question 5: What is the V8 engine?

***Answer:***  
The V8 engine is an open-source JavaScript engine developed by Google. It is written in C++ and is used to execute JavaScript code.  
V8 engine converts JavaScript code into machine code so that the computer can execute it efficiently.  
Node.js uses the V8 engine to run JavaScript outside the browser. For example, when we write JavaScript code to create an API in Node.js, the V8 engine executes that code.  
In simple words, V8 is the engine that executes JavaScript, while Node.js provides the environment and features needed to build backend applications.  

----
----

## Question 6: What is the Event Loop in Node.js?  

***Answer:***  
The Event Loop is a mechanism in Node.js that helps manage asynchronous operations and allows Node.js to handle multiple tasks efficiently without blocking the main JavaScript thread.  
When Node.js starts an asynchronous operation, such as reading a file or fetching data from MongoDB, it can continue executing other code instead of waiting for that operation to finish.  
Once the operation is completed, its callback or other continuation is scheduled to run. The Event Loop helps execute these callbacks when the main JavaScript thread is available.  
*For example,* when a user requests employee details, Node.js starts a database query and can handle other requests while waiting. When the database result is ready, Node.js processes it and sends the response.  
In simple words, the Event Loop helps Node.js manage asynchronous tasks while keeping the main JavaScript thread free to do other work. 

----
----

## Question 7: Why is Node.js called single-threaded? 

***Answer:***  
Node.js is called single-threaded because it executes JavaScript code on a single main thread. This means it processes one piece of JavaScript code at a time on that thread.  
However, Node.js can handle multiple requests efficiently using its event-driven, non-blocking I/O model. When an operation like reading a file or fetching data from MongoDB takes time, Node.js can continue handling other tasks instead of waiting.  
Some operations are handled by the operating system or the libuv thread pool in the background, so the main thread does not have to do everything itself.  
For example, while Node.js is waiting for a database query to complete, it can process another user's request.  

-----
-----

## Question 8: What is asynchronous programming?

***Answer:***  
Asynchronous programming means executing tasks without waiting for a time-consuming operation to finish before doing other work.  
In Node.js, operations like reading files, fetching data from MongoDB, or calling an external API can take some time. Instead of blocking the main thread while waiting, Node.js can continue handling other tasks.  
Once the operation is completed, we can process its result using callbacks, Promises, or async/await.  
*For example,* when a user requests employee details from our API, Node.js can start fetching the data from MongoDB and handle other requests while waiting for the database response.  
We commonly use asynchronous programming in Node.js to make backend applications more efficient and responsive.

-----
-----

## Question 9: What is synchronous vs asynchronous programming?  

***Answer:***  
Synchronous and asynchronous programming are two ways of executing code.  
Synchronous programming means code runs step by step. Each operation must finish before the next operation starts. If one operation takes a long time, the following code has to wait.  
Asynchronous programming means we can start a time-consuming operation and continue doing other work without waiting for it to finish. Once the operation completes, we can handle its result.  
*For example,* in a backend application, if we fetch employee data from MongoDB, synchronous execution would make the code wait for the result before moving forward. With asynchronous programming, Node.js can handle other requests while waiting for the database response.  
The main difference is that synchronous code waits for each operation to finish, while asynchronous code allows other work to continue during time-consuming operations.  

-----
-----

## Question 10: What is blocking vs non-blocking code? 

***Answer:***  
Blocking and non-blocking describe how code handles operations that take time to complete.  
Blocking code means the execution of the next operation is stopped until the current operation finishes. During this time, the main thread cannot do other JavaScript work.  
Non-blocking code means the program can start an operation and continue executing other code without waiting for that operation to finish.  
*For example,* in Node.js, if we read a file using the synchronous method fs.readFileSync(), the main thread waits until the file is completely read. But with the asynchronous method fs.readFile(), Node.js can continue handling other requests while the file is being read.  
So, the main difference is that blocking code makes the main thread wait, while non-blocking code allows it to continue doing other work.  

----
----

## Question 11: What is a callback function?

***Answer:***  
A callback function is a function that we pass as an argument to another function so that it can be called later when needed.  
In Node.js, callbacks are commonly used to handle asynchronous operations, such as reading files or fetching data.  
*For example,* when we read a file using Node.js, we can pass a callback function that executes once the file reading operation is completed. If an error occurs, the callback can handle that error.

```
import fs from "fs";

fs.readFile("data.txt", "utf8", (err, data) => {
  if (err) {
    console.log(err);
    return;
  }

  console.log(data);
});
```
Here, the callback function runs after the file reading operation completes.  
In simple words, a callback is a function passed to another function to be executed when needed, often after an operation is completed.

-----
-----

## Question 12: What is callback hell?

***Answer:***  
Callback hell happens when we use multiple nested callbacks inside each other, making the code difficult to read, understand, and maintain.  
It usually happens when we need to perform multiple asynchronous operations one after another, and each operation depends on the result of the previous one.     
*For example,* in a backend application, we might first fetch user details, then fetch that user's orders, and finally get the payment details. If we handle each operation using nested callbacks, the code can become deeply nested.  
We can avoid callback hell by using Promises or async/await, which make asynchronous code easier to read and manage.  

-----
-----

## Question 13: What is a Promise?

***Answer:***  
A Promise in JavaScript is an object that represents the result of an asynchronous operation. It tells us whether the operation is still in progress, completed successfully, or failed.  
A Promise has three states: pending, fulfilled, and rejected. Pending means the operation is still in progress, fulfilled means it completed successfully, and rejected means it failed.  
We can handle a Promise using `.then()` for a successful result, `.catch()` for an error, and .finally() for code that should run after the Promise settles.  
*For example,* when we fetch employee data from MongoDB, the operation can return a Promise. If it succeeds, we get the employee data; if it fails, we handle the error.  
Promises help us handle asynchronous operations without writing deeply nested callbacks, making our code easier to read and maintain.  

-----
-----

## Question 14: What is async/await?  

***Answer:***  
Async/await is a way to handle asynchronous operations in JavaScript. It makes asynchronous code easier to read and understand, similar to synchronous code.  
The `async` keyword is used before a function to make it return a Promise. The `await` keyword is used inside an `async` function to wait for a Promise to settle before continuing with the next line of that function.  
*For example,* in a backend application, when we fetch employee details from MongoDB, we can use await to wait for the database result before sending the response to the client.

```
async function getEmployee() {
  try {
    const employee = await Employee.findById("123");
    console.log(employee);
  } catch (error) {
    console.log(error);
  }
}
```  
Here, await waits for the database operation to complete, and try...catch handles any error.  
In simple words, async/await makes asynchronous code easier to write and manage without blocking the main thread during asynchronous I/O operations.  

----
----

## Question 15: Promise vs async/await — what is the difference?  

***Answer:***  
Promises and async/await are both used to handle asynchronous operations in JavaScript, but they differ in how we write and manage the code.  
A `Promise` represents the result of an asynchronous operation. We can handle its result using `.then()` and handle errors using `.catch().`    
Async/await is a cleaner way to work with Promises. It makes asynchronous code easier to read because it looks similar to synchronous code. We can use try...catch to handle errors.  
*For example,* when fetching employee details from MongoDB, we can use either Promises or async/await to handle the database result.  
In simple words, both do the same job, but async/await often makes the code easier to read and maintain, especially when multiple asynchronous operations depend on each other.  

----
----

## Question 16: How do you handle errors in async/await? 

***Answer:***  
We handle errors in async/await using try...catch. We write the asynchronous code inside the try block and handle any error in the catch block.  
*For example,* when fetching employee data from MongoDB, if the database operation fails, the catch block handles the error instead of allowing it to go unhandled.  

```
try {
  const employee = await Employee.findById(id);
} catch (error) {
  console.error(error);
}
```
In Express.js, we can also pass errors to centralized error-handling middleware to send a proper error response to the client.  

----
----

## Question 17: What is npm?

***Answer:***  
NPM stands for Node Package Manager. It is a tool that comes with Node.js and helps us install, manage, and update packages in our project.   
Packages are reusable pieces of code that help us add features without writing everything from scratch.  
*For example,* in a backend project, we can use npm to install Express.js for building APIs and Mongoose for working with MongoDB.  
We commonly use commands like npm install to install packages and npm uninstall to remove them.  
In simple words, npm helps us manage the external packages and dependencies required by our Node.js project.

----
----

## Question 18: What is package.json?  

***Answer:***  
`package.json` is an important file in a Node.js project that contains information about the project, such as its name, version, scripts, and dependencies.
It keeps track of the packages our project needs to run. It also allows us to define commands like npm run dev and npm start to run our application.  
`For example,` in an Express.js project, we can find packages like Express and Mongoose listed in the dependencies section.  
In simple words, package.json manages project information, dependencies, and scripts in a Node.js application.  

----
----

## Question 19: What is package-lock.json? 

***Answer:***  
`package-lock.json` is a file in a Node.js project that records the exact versions of the installed packages and their dependencies.
It helps ensure that when another developer installs the project dependencies, they get the same package versions, making the application more consistent across different environments.  
*For example,* when we install Express.js using npm install, npm updates package-lock.json to record the installed versions.  
In simple words, package.json defines the required dependencies, while package-lock.json records the exact versions installed.  

----
----

## Question 20: What is the difference between dependencies and devDependencies?

***Answer:***  
In Node.js, both dependencies and devDependencies are used to manage the packages required by our project, but they serve different purposes.  
Dependencies are packages required for the application to run in production. For example, Express.js is used to build APIs, and Mongoose is used to connect with MongoDB.  
DevDependencies are packages used during development, testing, or code checking but are not required to run the application in production. For example, Nodemon automatically restarts the server when we make code changes.  
We use `npm install package-name` to install a regular dependency and `npm install package-name -D` to install a development dependency.  
In simple words, dependencies are needed to run the application, while devDependencies are mainly needed during development.  

----
----

## Question 21: What is node_modules? 

***Answer:***  
`node_modules` is a folder in a Node.js project that contains the packages and libraries installed using npm.  
For example, when we install Express.js and Mongoose, their package files are stored inside the node_modules folder, along with the other packages they depend on.  
We generally don't upload this folder to GitHub because it can be recreated by running npm install, using the dependencies listed in package.json and the lockfile.  
In simple words, node_modules stores the external packages that our Node.js application needs to work.  

----
----

## Question 22: What is a module in Node.js?

***Answer:***  
A module in Node.js is a separate file that contains code for a specific task. It helps us organize our code into smaller, reusable, and manageable parts.  
*For example,* in an Express.js project, we can create a separate module for user-related functions and another module for employee-related functions. We can export functions from one module and use them in another module.  
Node.js supports two module systems: CommonJS, which uses require() and module.exports, and ES Modules, which uses import and export.  
In simple words, modules help us organize and reuse code instead of writing everything in a single file.  

----
----

## Question 23: What are built-in modules in Node.js?  

***Answer:***  
Built-in modules are modules that come with Node.js, so we don't need to install them separately using npm.  
They provide ready-made functionality for common tasks like working with files, handling server requests, managing file paths, and interacting with the operating system.  
- fs — used to read and write files.  
- http — used to create HTTP servers.  
- path — used to work with file and directory paths.  
- os — provides information about the operating system.  
- crypto — provides cryptographic functions.  
We can import these modules directly into our application using import.  
In simple words, built-in modules are ready-to-use features provided by Node.js that help us perform common tasks without installing external packages.  

----
----

## Question 24: What is the difference between CommonJS and ES Modules?

***Answer:***  
CommonJS and ES Modules are two module systems used in Node.js to import and export code between files.  
`CommonJS` uses `require()` to import code and `module.exports` to export code. It is the traditional module system in Node.js.  
ES Modules (ESM) uses import to import code and `export` to `export` code. It is the standard JavaScript module system.  
*For example,* in CommonJS, we write const express = require("express"), whereas in ES Modules, we write import express from "express".  
The main difference is their syntax and how modules are loaded. ES Modules support static imports and exports, while CommonJS uses require() to load modules.  
In simple words, both help us share code between files, but they use different import and export syntax.  

----
----

## Question 25: What is require() vs import?

***Answer:***  
require() and import are used to bring code from one file or module into another file in Node.js.  
require() belongs to the CommonJS module system, while import belongs to the ES Modules system.  
*For example,* in CommonJS, we write const express = require("express"), whereas in ES Modules, we write import express from "express".  
In simple words, both are used to use code from other modules, but they belong to different module systems.

----
----

## Question 26: What is the fs module?

***Answer:***  
The `fs` module stands for File System. It is a built-in Node.js module used to work with files and directories.  
We can use it to read, write, update, delete, and manage files.  
*For example,* in Node.js, we can use fs.readFile() to read a file and fs.writeFile() to write data into a file.  
In simple words, the `fs` module helps us perform `file-related` operations in Node.js without installing any external package.

---
---

## Question 27: What is the path module? 

***Answer:***  
The `path` module is a built-in Node.js module used to work with file and directory paths.  
It provides methods to join paths, get file names, find file extensions, and handle paths correctly across different operating systems.  
*For example,* we can use `path.join()` to combine directory and file names into a valid path.  
In simple words, the path module helps us create and manage file paths safely in Node.js.  

----
----
