# 100 React Js Interview Questions with proper explanation and understanding
*by Anshuman Kundu*
## Day 1:

Q1. What is React and What is its role in Software Development?
1. React is an open-source Javascript library
2. React is used for building UI interfaces
3. React simplifies the creation of web applications by combining HTML, CSS and JS at one place using JSX extension.
4. It involves server side rendering.

Q2. What are the key features of React?
1. Virtual DOM
2. Component based architecture
3. JSX (Javascript XML)
4. Reusability
5. Ecosystem
6. Hooks
7. Declarative syntax
   
Q3. What is DOM? What is the difference between HTML and DOM?
1. Document Object Model
2. It's a tree like structure of objects where every object corresponds to the element of the document like tags, attributes, etc.
3. HTML is static and when we change anything in the code of HTML document the direct changes reflect on the web page but it goes on by changing the DOM of the web page and the browser re-renders the whole code/web-page  which can be time taking.
   
Q4. What is Virtual DOM?
1. It's the blue print/copy of the actual/real DOM.
2. React in turn does the same thing, it plays with the Virtual DOM.
3. Whenever we change any small thing in our code which is written using React, it actual changes the Virtual DOM instead of directly manipulating the real DOM improving the performance of the web page.
4. The changes in the Virtual DOM is then compared to the real DOM and only the differences are manipualted to the real DOM which in turn re renders only the changed parts instead of whole web page being re rendered.
5. The difference manipulation from Virtual DOM and DOM is called Reconcilation and is done by React libraries.

Q5. What are React components?
1. Reusable building blocks for creating user interfaces.
2. It encapsulates functionalities and content at one place in JSX and makes it available to other components as well for usage.

Q6. Single Page Applications and Multi Page Applications (SPA & MPA)?
1. SPA's are made of only single page and multiple components where any event triggered actually resides in only one page.
2. MPA's have multiple pages where several pages have several components.

Q7. What is the role of JSX in React?
1. React elements and components can be created using Javascript which has its pre defined syntax using React.createElement(), etc. which is rigorous to use when building a big website.
2. JSX provides a simple syntactical way to create elements and components using HTML&CSS inside Javascript which makes it readable and simple.
3. Babel is a library which converts JSX into actual Javascript code and can be viewed anytime.

Q8. What is declarative syntax & imperative syntax?
1. Output driven code is called declarative syntax which provides you what to do without involving the steps of how to do.
2. Imperative syntax involves commands which tells you what to do and how to do both?


## Day 2:

Q9. What is an Arrow funtion in JSX?
1. Simple and Concise way of defining regular javascript functions.

Q10. How to setup a React project?
1. Terminal -> npx create-react-app name-of-project
2. Go into the project directory and -> npm start

Q11. What are the main files must required to start a React web application?
1. node_modules - contains all your libraries that you are going to use to build the application. Anything added using **npm install library-name** appears in these in node_modules. (It's huge in size)
2. public folder - contains **index.html**
3. src folder - contains **App.js & index.js**

Q12. How does React loads the web page and displays it to the user?
1. User requests the frontend server by clicking on some website link.
2. The frontend server finds the **index.html** folder.
3. **index.html** then finds and loads the entry point of javascript which is **index.js** using React libraries.
4. **index.js** then finds the root element in the **index.html** and replaces it by **App.js**.
5. **App.js** is the root component of the web application and contains all the child components which is displayed via **index.html**.
6. package.json - It is the json file which contains the summary of the project including, name, react library versions, etc.

Q13. What are the differences between React and Angular?
1. React is a Javascript library -> Angular is a complete framework.
2. React is simple to learn -> Angular is complex to learn.
3. React uses Virtual DOM -> Angular uses real DOM.
4. React is fast -> Angular is slow as compared to React.
5. React uses external libraries for complex functionalities -> Angular has built in support for everything because it's a framework.

Q14. What are the differences between library and framework?
1. Library is a combination of reusable codes distributed in terms of objects, modules, classes, components, etc. -> Angular is a set of tools, libraries, etc.
2. Your application(you) controls the usage and integration of library in your code where as Framework controls the structure of the web application.
3. Library is lightweight and can be manipulated as desired -> Angular is heavy weight which has built in functionalities and its not flexible.

Q15. What is Reusability and composition in React?
1. Reusability is using already created components any where ever you want in your React application which reduces code weight.
2. Composition is creating new and bigger components using small components. When you make changes to these small components will not impact the other components.
3. Both are the part of React's component based architecture. 

Q16. What is state management in React?
1. In React state refers to the current value of a variable.
2. If user triggers any action on the state of a variable like updation or deletion, it should automatically re-render and user should be able to see the changes in the UI immediately. This is called state management and is achieved by React hook **useState()**.

Q17. What are props in JSX?
1. Props are data which are passed from parent component to child component.

Q18. What is NPM and what is the role of node_modules in React?
1. NPM - Node Package Manager is responsible for managing and keeping all the modules, libraries and dependencies in a folder called node_modules which are necessary for the React application development.

Q19. What is the role of public folder in React?
1. Public folder is responsible for keeping all the static assets of a web application.
2. These assets are directly served the web browser when website is opened first.
3. It contains favicons, static images, **index.html**, etc.
   
Q20. What is the role of index.html in React?
1. *index.html* is the entry point of our web application.
2. It contains a div with id root in the body which contains the content being served and displayed in the UI.
   
Q21. What is the role of src folder in React?
1. src folder is responsible for containing all the dynamic assets needed for our React application.
2. **App.js, index.js** are must in src folder, without these your web application won't run.
3. You can create components inside this folder.

Q22. What is the role of index.js in React?
1. index.js finds the root element in the index.html file using ReactDOM.
2. ReactDOM is a react library which is used to point referrence to the DOM and deals with the DOM directly.
3. After finding the root element it replaces the content of root with App.js file.

Q23. What is the role of App.js in React?
1. App.js is the root component of our web application.
2. It can incorporate components, routing and usually used to structure the layout of our application.

Q24. Why is export default used in React?
1. Whenever a .js file is created everything is kept inside a javascript function.
2. This function is available to be imported by other components in the application only if it has been exported where it has been written.

## Day 3:

Q25. What is the role of JSX in React?
1. JSX(Javascript XML) is a syntax extension in React.
2. It allows users to write HTML like code inside Javascript functions.
3. It improves code reading and writing ability.

Q26. What is Babel?
1. Bable is a react library.
2. When we write code in JSX, the code is transpiled to Javascript before sending it to browser using babel because browser only understands Javascript.

Q27. What is the role of Fragment in JSX?
1. Fragment wraps small elements and containers within it. **(<>{code}</>)**
2. It caters the unnecessary usage of react blocks(divs) which might effect the UI of the web application.
   
Q28. What is use of spread operator in JSX?
1. {...props} is used to pass all the properties of a javascript object to other components in React.
2. It avoids mannual listing of every key value pair being passed to any component as prop.

Q29. What is the difference between a transpiler and compiler?
1. Transpiler converts high level language to another high level language.
2. Converting JSX to Javascript is called transpilation.
3. Compiler converts high level language to another low level language.
4. Converting C++ to machine level code/ bytecode is called compilation.



## Day 4:

Q30. What are React components?
1. Reusable building blocks of a React web application.

Q31. What are the types of React components?
1. Functional Components
2. Class Components

Q32. What are Functional Components?
1. Defined as Javascript functions : 
   **function AppComponent(){
        return (
            write html code here.
        )
    }**

2. Does not have a render method
3. They are stateless but now using hooks they can manage states
4. They do not use lifecycle methods
5. They donot use this keyword

Q33. What are class components?
1. Defined as Javascript classes
    class AppComponent extends Component{
        render(){
            return(
                your html code goes here
            )
        }
    }
2. Does have a render method
3. They are stateful and can manage states using **this.state**.
4. They have lifecycle methods
5. They use this key word for accesing state, props of the particular class instance.
   
Q34. What is prop drilling?
1. It refers to the passage of props from parent -> child -> grand child -> and so on.

Q35. Why to avoid prop drilling?
1. It makes code readablity poor anc complex.
2. Debugging is difficult as you have to go through numerous components.
3. Affects code performance.

Q36. What are the methods to avoid prop drilling?
1. Use Context API
2. Use callback functions
3. Custom hooks

Q37. What is this keyword?
1. **this** keyword points to the instance of the class and any parameter being stored can be accessed using this keyword inside the same class.
2. Just like other languages which supports OOPs concept, this works same in all.
