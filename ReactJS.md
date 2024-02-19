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