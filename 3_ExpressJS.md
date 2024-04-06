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

