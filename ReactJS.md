# 100 React Js Interview Questions with proper explanation and understanding

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