**Copyright @ Anshuman Kundu**

# React under the hood
*by Anshuman Kundu*

### Elements, Components and Component Instances

##### Go through the images below to understand how react works with elements, components and component instances:

![Elements](/assets/RUH-1.png)

![Elements](/assets/RUH-2.png)

###### This is how our jsx gets converted to createElement function calls by Babel:
![Elements](/assets/RUH-3.png)

###### This is how our complex JSX codes looks like when a component is created in React: 
![Elements](/assets/RUH-4.png)

![Elements](/assets/RUH-5.png)

###### So Just like before App() was giving us an object similarly <"App"/> wherever used will be called as App() function.
![Elements](/assets/RUH-6.png)

![Elements](/assets/RUH-7.png)

![Elements](/assets/RUH-8.png)

### Reconciliation

![Elements](/assets/RUH-9.png)

![Elements](/assets/RUH-10.png)

![Elements](/assets/RUH-11.png)

![Elements](/assets/RUH-12.png)

### Rendering

![Elements](/assets/RUH-13.png)

![Elements](/assets/RUH-14.png)

### React Fiber

Fiber is the react's new reconcilation engine (earlier it was React Stack). 
Primary Features:

1. It breaks down work into smaller asynchronous chunks and frames which makes the work to be categorised in terms of priority and browser can do rendering on the priority basis.
2. Prioritization of updates based on the urgency of the work. So less urgent work if comes first and more urgent comes second, then fiber will help browser update the more urgent work by interrupting the rendering process.
3. React will now prepare multiple versions of the same UI and render them depending on the type of user interaction happening, this is called **Concurrency**.

###### React Fiber represents a significant step forward in the evolution of React, providing a more efficient, flexible, and robust architecture for building modern web applications. By enabling incremental rendering, prioritization of updates, and improved error handling, Fiber enhances both the performance and developer experience of React applications.  

### Flow of Data in React

Data flows in React in a unidirectional way which is from the Parent to the children component.
Here are the 5 ways:

1. Props: These are basically input arguments just like functions have. These can be passed to the child components when the child needs the same prop data as well.
2. State: Manage data that is local to the component.
3. State Lifting: Let suppose there are two child components coming from a single parent and both needs a similar state value to be stored or updated, then instead of creating these values on both places, we create these states on the parent and pass it down to the children. In this way we lifted the state up to the parent component.
4. Context API: React Context can help store and update data which can be used globally.
5. Redux: State Management Library which uses a store to actually store the data.

### Server Side Rendering (SSR) vs Client Side Rendering (CSR) in React

**Scenario: Click on a website link and it goes to the server to request the content which gets returned back with a response and the client sees it.**

###### CSR
1. Server returns the HTML, CSS, JS Bundle to the client.
2. Client starts downloading the JS Bundle and till it downloads a blank screen is shown.
3. After download the HTML+CSS+JS is rendered as the First Page on the browser.
4. The First Page is combined of loading items which says the data is still being loaded.
5. The DB Queries are hit on the server side to fetch the data and after the data is fetched, it re renders and now the ready content is seen on the UI.

**3 points to be noted:**
1. SEO and UX is bad because of Black Screen and late first page response.
2. DX is good.   
   
###### SSR
1. Server runs the necessary DB Queries and processes the HTML CSS of the First Page and then returns the rendering Shell wthh Partially fetched data and HTML, CSS + To be downloaded JS Bundle.
2. Client immediately shows the received HTML+CSS with partial data avoiding the black screen and starts downloading the JS Bundle. Since the client has HTML CSS processed no blank screen is visible instead First Page is directly shown but JS is still getting downloaded, therefore the First Page is not interactive.
3. After download of JS Bundle, **Hydration** takes place which traverses the DOM to bind the event listeners to the dom elements received from the Bundle.
4. After Hydration the Complete Page is interactive.
5. The DB Queries are hit on the server side to fetch the data and after the data is fetched, it re renders and now the ready content is seen on the UI.

**3 points to be noted:**
1. SEO and UX is good because of no Black Screen and fast first page response.
2. DX is good. 

### Synthetic Event

Browser's may have their default UI behaviours where they will wrap the incoming UI with some wrappers and this will cause the Dev UI to be combined with some browser defaults. To prevent this react provides events like e.preventDefault(), e.stopPropagation(), etc.
These are called **Synthetic Events** which prevents browser default behaviours.

### 3 most important ways to optimize React Application

1. Lazy Loading
2. useMemo Hook
3. removeEventListeners() method





