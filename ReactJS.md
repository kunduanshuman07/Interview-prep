# React Js Interview Questions with indepth explanations.
*by Anshuman Kundu*

## 1. What is ReactJs?
1. It is an Open-source Javascript library used for building User interfaces introduced by Facebook.
2. Combines HTML, CSS and JS to create Single Page Web applications using JSX.
3. Frequent Data changes can take place in applications without requiring a page reload.
4. React mainly focusses on its component based structure which inherits the code reusability concept in Web development.

## 2. Explain the key features of ReactJs.
1. Virtual DOM
2. Component based structure (code reusability)
3. JSX - Javascript extension for writing HTML, CSS and JS code all together.
4. Huge Ecosystem.
5. Hooks
6. Inbuilt state management tools.
7. Unidirectional (data flow can be only from parent to children)

## 3. What is JSX?
1. Javascript extension is an extension which helps coders write readable code combining HTML, CSS and JS.
2. Every tag in HTML is a DOM element which helps build the website.
3. While creating a DOM element in React without JSX we will have to **const element = React.createElement('h1', null, 'Hello, World!');**
   The first parameter is the type of DOM Element, the second is props and the third is the content the element will display in the browser.
4. While creating websites we need to create lots and lots of DOM elements and by the above code it seems very rigourous to code.
5. With JSX we can simply write **<h1">Hello World</"h1>** inside a component and it displays what we need.

## 4. But the browser does not understand JSX, how will it process the code?
1. The browser understand JS syntax only and not JSX syntax.
2. There are inbuilt libraries in Javascript like **Babel** which converts the JSX code to JS syntax before processing.

## 5. What is DOM and what is Virtual DOM?
1. DOM - Document Object Model.
2. It is a tree like structure representing all the elements and attributes need to build a Website. It includes elements like div, h1, p, attributes like class, id, and text nodes.
3. When we create a website using HTML, CSS and JS, let suppose user triggers any action and certain things like variable values change, it directly changes the things in the DOM tree which is the actual website tree. This slows a lot of things in the website due to the re rendering of the entire DOM although the changes are too small.
4. React actually copies the real DOM and when a user triggers any action, the changes are first given to the Virtual DOM. Then the virtual dom compares the changes with the Real DOM and only the changes are updated instead of the whole DOM being re rendered which actually fastens DOM procedure and eventually the website.

## 6. What are components in React?
1. Components are reusable code fragments where actually the code is written.
2. It can be used any where in the React src directory.
3. So when u have written a code for a Navbar and several pages in the website needs the navbar, you donot have to write the code for it everytime in every page that needs it. Just write it once save it using Navbag.jsx and it can be imported wherever needed like <"Navbar/">

## 7. What are functional and class components?
1. Class Components: Defined as Javascript classes -> class AppComponent extends Component{ render(){ return( your code goes here ) } }
2. Functional Components: Defined as Javascript functions -> function AppComponent(){ return ( write code goes here. ) }

## 8. What are purpose of props in React?
1. In a React component **A** there is a variable named **name**.
2. There is a child component **B** being called inside **A** which also needs **name**, then you donot need to create a new variable inside **B** rather you can just pass the variable **name** from A to B like:
   function A() {
    return {
        variable name='Anshuman';
        <"B nameProp={name}">
    }
   } 
   function B(props) {
    return {
        <"h1>{props.nameProp}</h1">
    }
   }

## 9. What is a state and how do you update state in React?
1. State is the current value of a variable.
2. React provides inbuilt State hook for state management called **useState()**.
3. Can be updated using : 
   const [count, setCount] = useState(1);
   here is the we declared a variable count with initial value 1 and a function setCount which directly changes the count value.
   **setCount(count+1)** will directly change the current count value adding 1 to it.

## 10. What is the significance of keys in React Lists?
1. Keys are unique ids provided to list items which helps in processing the DOM changes.
2. When certain list items are changed in React Lists, the Virtual DOM identifies the unique list keys which are changed and differs the Real DOM accordingly.
