# Express.Js Interview Question & Answer

## Q 1: What is Express.js?

***Answer:***  
Express.js is a lightweight web framework for Node.js that makes backend development easier. It provides features to handle HTTP requests, define routes, use middleware, and send responses to clients.  
Without Express.js, we can create a server using Node.js's built-in http module, but we need to write more code to manage requests and routes. Express.js simplifies this process.  
*For example,* we can use Express.js to create REST APIs for user registration, login, and employee management.  
In simple words, Express.js makes it easier to build backend applications and APIs using Node.js.  

----
----

## Q 2: Why do we use Express.js with Node.js?

***Answer:***  
We use Express.js with Node.js because it makes backend development easier and faster. Node.js provides the environment to run JavaScript on the server, while Express.js provides useful features to handle requests and responses, define routes, and manage middleware.  
Without Express.js, we would need to write more code using Node.js's built-in HTTP module to handle routing and requests.  
In simple words, Node.js allows us to run JavaScript on the server, and Express.js makes it easier to build backend applications and APIs.  

-----
----- 

## Q 3: How do you create an Express server?

***Answer:***  
To create an Express server, first we install Express.js using npm. Then we import Express, create an application using express(), define routes to handle requests, and start the server using app.listen().  
*For example:*
```
import express from "express";

const app = express();

app.get("/", (req, res) => {
  res.send("Server is running");
});

app.listen(5000, () => {
  console.log("Server running on port 5000");
});
```  
Here, express() creates the application, app.get() handles GET requests to the home route, and app.listen() starts the server on port 5000.  
In simple words, we create an Express application, define routes, and use app.listen() to start the server.

----
----

## Q 4: What is routing in Express.js?

***Answer:***  
Routing in Express.js means defining how our server responds to client requests based on the URL and HTTP method.  
We use routing to handle different operations, such as creating, fetching, updating, and deleting data.  
*For example,* in an employee management system, we can define GET /employees to fetch all employees and POST /employees to create a new employee.  
*For example:*
```
app.get("/employees", (req, res) => {
  res.send("Get all employees");
});

app.post("/employees", (req, res) => {
  res.send("Create a new employee");
});
```  
Here, `app.get()` handles `GET` requests, and `app.post()` handles `POST` requests.  
In simple words, routing decides which code should execute when a client sends a request to a particular URL using a specific HTTP method.  

----
----

## Q 5: What are req and res objects?

***Answer:***  
In Express.js, req and res are objects used to handle client requests and send responses.  
`req` (Request) contains information about the incoming request, such as the request body, URL parameters, query parameters, and headers.  
`res` (Response) is used to send a response back to the client, such as JSON data, a status code, or a message.  
*For example:*
```
app.get("/employees", (req, res) => {
  res.status(200).json({
    message: "Employees fetched successfully"
  });
});
```  
Here, req provides information about the client's request, and res sends a JSON response with status code 200.   
In simple words, req helps us read the incoming request, and res helps us send the response back to the client.  

----
----

## Q 6: What is req.params?  

***Answer:***  
`req.params` is an object in Express.js that contains values passed as named parameters in the URL.  
We use it when we want to access a specific resource, such as fetching an employee by their ID.  
*For example:*
```
app.get("/employees/:id", (req, res) => {
  res.json({ employeeId: req.params.id });
});
```  
If the client sends a request to /employees/101, then req.params.id will return "101" as a string.  
In simple words, req.params helps us access dynamic values from the URL, such as an employee ID or user ID.  

----
----

## Q 7: What is req.query? 

***Answer:***  
`req.query` is an object in Express.js that contains values passed as query parameters in the URL.  
We commonly use it for filtering, searching, sorting, and pagination.  
*For example:*  

```
app.get("/employees", (req, res) => {
  res.json({ department: req.query.department });
});
```  
If the client sends a request to /employees?department=IT, then req.query.department will return "IT".  
In simple words, req.query helps us access optional values from the URL, mainly used for searching, filtering, and pagination.  

----
----

## Q 8: What is req.body?

***Answer:***  
`req.body` is a property in Express.js that contains data sent by the client in the request body.  
We commonly use it when creating or updating data, such as registering a user or adding a new employee.  
*For example:*  
```
app.use(express.json());

app.post("/employees", (req, res) => {
  const { name, email } = req.body;

  res.json({ name, email });
});
```  
Here, `express.json()` parses incoming JSON data, and req.body allows us to access the employee's name and email sent by the client.  
In simple words, req.body helps us access the data sent by the client in the request body.  

-----
-----

## Q 9: Difference between params, query and body?

***Answer:***  
In Express.js, req.params, req.query, and req.body are used to access data sent by the client, but they get data from different places.  
req.params is used to access dynamic values from the URL, such as an employee ID. For example, /employees/101.  
req.query is used to access query parameters, mainly for searching, filtering, and pagination. For example, /employees?department=IT.  
req.body is used to access data sent in the request body, mainly when creating or updating data, such as an employee's name and email.  
In simple words, params identify a specific resource, query helps filter or search data, and body carries the data we want to send to the server.  

----
----

## Q 10: What is middleware in Express.js?

***Answer:***  
Middleware is a function in Express.js that runs during the request-response cycle. It can access the request object `(req)`, the response object `(res)`, and the `next()` function.  
We use middleware for tasks like authentication, request validation, logging, and error handling.  
For example, before allowing a user to access a protected API, we can use authentication middleware to check whether the user has a valid token.  
```
const logger = (req, res, next) => {
  console.log(req.method, req.url);
  next();
};

app.use(logger);
```  
Here, the middleware logs the request method and URL, and next() passes control to the next middleware or route handler.  
In simple words, middleware helps us perform common tasks before sending a response to the client.  

----
----

## Q 11: Why do we use middleware?

***Answer:***  
We use middleware in Express.js to perform common tasks during the request-response cycle before sending a response to the client.  
Middleware helps us avoid repeating the same code in multiple routes and keeps our application organized and easier to maintain.  
*For example,* we use authentication middleware to check whether a user is logged in, validation middleware to check incoming data, and logging middleware to track client requests.  
In simple words, middleware helps us handle common tasks in one place and reuse them across multiple routes.  

----
----

## Q 12: What is next() in Express.js?

***Answer:***  
`next()` is a function in Express.js that passes control to the next middleware or route handler in the request-response cycle.  
We use it when the current middleware has completed its task and we want the request to continue to the next step.  
For example, in authentication middleware, after verifying the user's token successfully, we call `next()` to allow the request to continue to the protected route.  
*For Example:*  
```
app.use((req, res, next) => {
  console.log("Request received");
  next();
});
```  
Here, next() allows Express.js to continue processing the request.  
In simple words, next() tells Express.js to move to the next middleware or handler.  

-----
-----

## Q 13: What happens if we don't call next()?  

***Answer:***  
If we don't call next() in middleware and also don't send a response to the client, the request will remain pending, and the client may keep waiting.  
Express.js will not automatically move to the next middleware or route handler.  
*For example,* if authentication middleware checks a user's token but neither calls next() nor sends an error response, the request will get stuck.  
In simple words, we must either call next() to continue processing the request or send a response to the client.

----
----

## Q 14: What are different types of middleware?  

***Answer:***  
Express.js has five main types of middleware:  
1. `Application-level middleware:` Used across the application or for specific routes. For example, logging incoming requests.  
2. `Router-level middleware:` Used for specific routes grouped with express.Router(), such as authentication for employee routes.  
3. `Built-in middleware:` Provided by Express.js, such as express.json() for parsing JSON request bodies.  
4. `Third-party middleware:` Installed using npm, such as cors for handling cross-origin requests and morgan for logging.  
5. Error-handling middleware: Used to handle errors and send proper error responses to the client.  
In simple words, each type of middleware helps us handle a specific task, such as processing requests, protecting routes, or handling errors in an Express.js application.  

---
---

## Q 15: How do you create custom middleware?

***Answer:*** 
We can create custom middleware in Express.js by defining a function that receives three parameters: req, res, and next.  
We use this function to perform tasks such as logging requests, validating data, or checking authentication. After completing its task, we call next() to pass control to the next middleware or route handler.  
*For Example:*  
```
const loggerMiddleware = (req, res, next) => {
  console.log(`${req.method} ${req.url}`);
  next();
};

app.use(loggerMiddleware);
```  
Here, the middleware logs the HTTP method and URL of every incoming request, and next() allows the request to continue.  
In simple words, custom middleware is middleware we create ourselves to handle specific tasks in our application.  

----
----

## Q 16: What is express.json()?

***Answer:***  
express.json() is a built-in middleware in Express.js that parses incoming JSON request bodies and makes the data available in req.body.  
We use it when the client sends JSON data to our backend, such as during user registration or employee creation.  
*For example:*  
```
app.use(express.json());

app.post("/users", (req, res) => {
  const { name, email } = req.body;
  res.json({ name, email });
});
```  
Here, `express.json()` parses the incoming JSON data so we can access the user's name and email through req.body.  
In simple words, `express.json()` helps Express.js read JSON data sent by the client.  

----
----

## Q 17: What is error-handling middleware?  

***Answer:***  
Error-handling middleware in Express.js is used to handle errors in one central place and send proper error responses to the client.  
It takes four parameters: err, req, res, and next. When an error occurs, we can pass it to this middleware using next(err).  
*For example:*  
```
app.use((err, req, res, next) => {
  res.status(500).json({
    message: "Internal Server Error"
  });
});
```  
Here, the middleware catches errors passed to it and sends a proper response to the client.  
In simple words, error-handling middleware helps us manage errors centrally instead of handling them separately in every route.  

----
----

## Q 18: How do you handle errors globally in Express?  

***Answer:***  
We handle errors globally in Express.js by creating centralized error-handling middleware. Instead of handling every error separately in each route, we pass errors to a single middleware using next(err).  
This middleware receives four parameters: err, req, res, and next. It handles the error and sends an appropriate status code and message to the client.  
*For example,* if a database operation fails, we can pass the error to the global error handler, which sends a proper error response.  
In simple words, global error handling helps us manage errors in one place and keep our code clean and consistent.  

-----
-----

## Q 19: What is REST API? 

***Answer:***  
REST API stands for Representational State Transfer Application Programming Interface. It allows two applications to communicate with each other over HTTP.  
In backend development, we use REST APIs to send requests from the client to the server and receive responses, usually in JSON format.  
For example, in an employee management system, we can use GET /employees to fetch employees, POST /employees to create an employee, PUT /employees/:id to update an employee, and DELETE /employees/:id to delete an employee.  
REST APIs commonly use HTTP methods such as GET, POST, PUT, PATCH, and DELETE to perform different operations.  
In simple words, a REST API allows the frontend and backend to communicate through URLs and HTTP requests to exchange data.  

----
----

## Q 20: What is CRUD?  

***Answer:***  
CRUD stands for Create, Read, Update, and Delete. These are the four basic operations we perform on data in a backend application.    
- `Create:` To add new data, usually using the POST method.  
- `Read:` To fetch existing data, usually using the GET method.  
- `Update:` To modify existing data, usually using PUT or PATCH.  
- `Delete:` To remove data, usually using the DELETE method.    
For example, in an employee management system, we can create a new employee, view employee details, update their information, and delete their record.  
In simple words, CRUD represents the basic operations used to manage data in a database through backend APIs.

-----
-----

## Q 21: What are HTTP methods — GET, POST, PUT, PATCH, DELETE?  

***Answer:***  
HTTP methods define what action the client wants to perform on a resource through an API.  
The five commonly used HTTP methods are:  
- `GET:` Used to fetch data from the server. 
- `POST:` Used to create new data.  
- `PUT:` Used to replace an existing resource with updated data.  
- `PATCH:` Used to update specific fields of an existing resource.  
- `DELETE:` Used to delete a resource.  
For example, in an employee management system, we use GET /employees to fetch employees, POST /employees to create an employee, PUT /employees/101 to replace an employee's data, PATCH /employees/101 to update specific fields, and DELETE /employees/101 to delete that employee.  
In simple words, HTTP methods tell the backend what action the client wants to perform on the data.  

----
----

## Q 22: Difference between PUT and PATCH?  

***Answer:***  
`PUT` and `PATCH` are both `HTTP` methods used to update existing data, but they differ in how they update the resource.  
`PUT` is generally used to replace the entire resource with the provided data, while `PATCH` is used to update only specific fields of a resource.  
*For example,* suppose an employee has a name, email, and department. If we want to replace the employee's complete data, we use `PUT`. If we only want to change the department, we use `PATCH`.  
In simple words, PUT replaces the complete resource, while `PATCH` updates only the required fields.  

----
----

## Q 23: What are HTTP status codes?  

***Answer:***  
HTTP status codes are three-digit numbers sent by the server to tell the client whether a request was successful or if something went wrong.  
They are divided into five categories:  
- `1xx — Informational:` The request is still being processed.  
- `2xx — Success:` The request was successful. For example, 200 OK and 201 Created.  
- `3xx — Redirection:` Further action is needed to complete the request.  
- `4xx — Client Error:` Something is wrong with the request. For example, 400 Bad Request and 404 Not Found.  
- `5xx — Server Error:` Something went wrong on the server. For example, 500 Internal Server Error.  
*For example,* when we successfully create an employee, we can return 201 Created. If the employee is not found, we can return 404 Not Found.  
In simple words, HTTP status codes help the client understand the result of its request.  

-----
-----

## Q 24: Difference between 400, 401, 403, 404 and 500?  

***Answer:***  
These are `HTTP` status codes used to describe different types of errors in a backend application.  
- `400 Bad Request:` The request contains invalid data or is not properly formed.  
- `401 Unauthorized:` The user is not authenticated, for example, when a valid login token is missing.  
- `403 Forbidden:` The user is authenticated but does not have permission to access the resource.  
- `404 Not Found:` The requested resource does not exist.  
- `500 Internal Server Error:` An unexpected error occurs on the server.  
For example, in an employee management system, invalid input may return 400, a missing login token may return 401, insufficient permissions may return 403, a missing employee may return 404, and an unexpected server error may return 500.  
In simple words, 400 means a bad request, 401 means authentication is missing or invalid, 403 means access is forbidden, 404 means the resource is not found, and 500 means a server-side error.  

----
----

## Q 25: What is res.status()?  

***Answer:***  
`res.status()` is a method in Express.js used to set the HTTP status code of a response sent to the client.  
We use it to tell the client whether a request was successful or if an error occurred.  
*For example:*  
``` 
app.get("/employees", (req, res) => {
  res.status(200).json({
    message: "Employees fetched successfully"
  });
});
```  
Here, `res.status(200)` sets the status code to 200 OK, which indicates that the request was successful.  
In simple words, res.status() helps us send the appropriate HTTP status code with the response.  

---- 
----

## Q 26: Difference between res.send() and res.json()?  

***Answer:***  
Both `res.send()` and `res.json()` are methods in Express.js used to send responses to the client, but they handle the response differently.  
`res.send()` can send different types of responses, such as text, HTML, buffers, and objects.  
`res.json()` is specifically used to send JSON responses. It converts the provided data into JSON format and sets the appropriate Content-Type header.  
*For example:*  
```
res.send("Employee created successfully");

res.json({ message: "Employee created successfully" });
```  
Here, res.send() sends a text response, while res.json() sends a JSON response.  
In simple words, res.send() is used for different types of responses, while res.json() is specifically used to send JSON data, which is commonly used in REST APIs.  

-----
-----

## Q 27: What is CORS?  

***Answer:***  
CORS stands for Cross-Origin Resource Sharing. It is a browser security mechanism that controls whether a web application from one origin can access resources from another origin.  
*For example,* if our React frontend runs on `http://localhost:5173` and our Express backend runs on `http://localhost:5000`, the browser treats them as different origins because their ports are different.  
To allow the frontend to access the backend, we can configure CORS in Express.js using the cors package.  
*For Example*   
```
import cors from "cors";

app.use(cors({
  origin: "http://localhost:5173"
}));
```  
In simple words, CORS allows us to control which frontend origins can access our backend APIs through a browser.  

-----
-----

## Q 28: Why do we use CORS?  

***Answer:***  
We use CORS to allow a frontend application running on one origin to access a backend API running on another origin through the browser.  
By default, browsers restrict cross-origin requests for security reasons. If our React frontend and Express backend run on different origins, the browser may block the request unless the backend allows that origin through CORS.  
*For example,* if our React application runs on port 5173 and our Express server runs on port 5000, we can configure CORS to allow the frontend to access the backend APIs.  
In simple words, we use CORS to control which origins are allowed to access our backend APIs through a browser.  

----
----

## Q 29: What is API versioning?  

***Answer:***  
API versioning is a way to manage different versions of an API when we make changes to its functionality or response structure.  
It allows us to introduce new features or make changes without breaking existing applications that are still using the older version.  
For example, in Express.js, we can create /api/v1/users for the first version and /api/v2/users for the updated version of the same API.  
In simple words, API versioning helps us update our APIs while keeping them compatible with existing clients.  

-----
-----

## Q 30: Explain the complete request-response flow in Express.js.  

***Answer:***  
In Express.js, when a client sends a request to the server, it passes through several steps before the server sends a response back.  
First, the request reaches the Express server. Then, the registered middleware functions execute in order. These middleware functions can handle tasks like parsing JSON data, authentication, and validation.  
After that, Express matches the request URL and HTTP method with the appropriate route. The controller handles the request and may call a service to execute the business logic and interact with the database.  
Once the operation is completed, the server sends a response to the client, usually in JSON format with an appropriate HTTP status code. If an error occurs, it can be passed to the centralized error-handling middleware.  
In simple words, the flow is: Client Request → Middleware → Route → Controller → Service → Database → Response to Client.  

-----
-----


