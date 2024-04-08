**Copyright @ Anshuman Kundu**

# Node Js Interview Questions with proper explanation and understanding
*by Anshuman Kundu*


### 1. What are the advantages of using ExpressJS with nodeJs?
1. ExpressJS is built over NodeJs, so it simplifies the process of creating the backend of web applications.
2. It provides access to integrate middlewares between request response cycle.
3. It provides route management system for various HTTP requests like GET, POST, PUT, DELETE, PATCH, etc.
4. It helps create dynamic HTML files in the server side.

### 2. Explain the process of starting a Express server in a NodeJS application.
1. npm install express; - Installing express.
2. import Express from "express"; - Importing Express module.
3. import http from "http"; - Importing http module.
4. const app = Express(); - Intialising the Express app.
5. const server = http.createServer(app); - Creating a http server to run the app.
6. const PORT = 3000; - Defining the PORT on which the server will run.
7. server.listen(PORT, ()=>{
        console.log('Server started on PORT 3000');
   }) - Starting the express server.

### 3. What are middlewares?
1. Middlewares are special functions which performs specific tasks when a http request is recieved and passes it to the API endpoint.

### 4. How do middlewares work?
1. Let us say that we got an HTTP GET request A asking response from an API endpoint B.
2. Before directly sending the request A to B, there are middlewares defined which can verify whether the request is created by the secured user or not, etc.
3. Therefore the request from A passes on to the middlewares which has a next() function which sends the request to the next in queue functions and then if everything seems good it passes it to the endpoint B.
4. B returns the response to A.

### 5. How can we use middlewares?
1. npm install express; - Installing express.
2. import Express from "express"; - Importing Express module.
3. import http from "http"; - Importing http module.
4. const app = Express(); - Intialising the Express app.
5. const server = http.createServer(app); - Creating a http server to run the app.
6. const PORT = 3000; - Defining the PORT on which the server will run.
7. const middlewareFunc = (req, res, next) =>{
        res.send('How are you?');
        next();
   } - Defining middlewares
8. app.use(middlewareFunc); - Using middlewares
9. server.listen(PORT, ()=>{
        console.log('Server started on PORT 3000');
   }) - Starting the express server.

### 6. What is the request pipeline?
1. HTTP request -> middleware func1 -> middleware func2 -> api endpoint.
2. The above is called a request pipeline.

### 7. What is the use of next() function in middlewares?
1. It helps pass the request from one middleware func to another middleware func which is in the stack.

### 8. What is the use of app.use(middlewarename);
1. It helps the middlewares to go into the stack of functions to be pulled out one by one for systematic execution when a request arrives.


### 9. What are the types of middleware?
1. Application level middleware
2. Router level middleware
3. Built-in middleware
4. Error handling middleware
5. Third party middlware

### 10. What is an application level middleware?
1. Middlewares governing the whole application.
2. All the incoming requests and taken to this middleware.
3. const middlewareFunc = (req, res, next) =>{
        res.send('How are you?');
        next();
   } - Defining middlewares
4. app.use(middlewareFunc); - Using application level middleware


### 11. What is a the router level middleware?
1. Middlewares governing specific routes only.
2. All the incoming requests specific to this path only is taken to this middleware.
3. const middlewareFunc = (req, res, next) =>{
        res.send('How are you?');
        next();
   } - Defining middlewares
4. app.use('/example',middlewareFunc); - Using middlware for requests to '/example' routes only.

### 12. What is a built-in middleware?
1. There are some middlewares which are provided by Express already.
2. Example: app.use(express.static("public"));
3. The above middleware will help in serving the static files to the client side which are present inside the public directory.

### 15. What is an Error handling middleware?
1. It captures the error in the web application and executes the middleware functionality defined as below.
2. app.use((err,req,res,next)=>{
        console.error(err.stack);
        res.status(200).send('Something went wrong');
   })
3. When there are 4 middleware functions in the stack then the error handling middleware should be declared in the last. 

### 14. What is third party middleware?
1. They need to be installed via npm before using.
2. Examples: body-parser, helmet, etc.

### 15. What is Routing in Express.js?
1. When there is an incoming HTTP request, it is first directed to the middleware.
2. We have several controllers defined for specific functionalities, these controllers need to be directed to when a specific request arrives based on the route path.
3. This whole process is called routing.

### 16. How do you implement routing?
1. We define routes.
2. app.get('/login', (req,res)=>{
        console.log("Login route");
   })
3. Similarly changing the route methods such as get, post, patch, put, delete we can meet the route requirements.

### 17. Explain the route parameters.
1. app.get() -> Http request method
2. '/login' -> The url for the request.
3. (req,res)=>{
        console.log("Login route");
   } -> This is handler function which will be executed with arguments as req and res.