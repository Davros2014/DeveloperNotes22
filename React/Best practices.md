# **1. Break larger components into smaller ones**

To make components reusable, break the larger component into smaller ones. That means instead of putting multiple functionalities in one component create one component that will be responsible for single functionality, the principle is called as “single responsibility principle”.

Separating components will help us to read, maintain, debug, reuse and scale code in long run, as the project keeps on getting bigger and bigger with time due to the addition of new features.

# **2. Use Functional Components instead of classes**

If you are new to react you might get confused about what to use, functional component or class component.

Here is the answer!

Functional components are the stateless component that simply accepts data and display the output in some form, while Class components are stateful components that implement logic and state.

If you are writing the presentational component which doesn’t need to access the lifecycle method or have its own component state then you should use a functional component. On the other hand, if you need to manage the state then use the class component.

Here are the benefits of using Functional components:

-   They are easy to test, debug and refactor as they are written in plain Javascript functions without state and lifecycle hooks.
    
-   Reduce the number of lines of code
    
-   Eliminate the use of ‘this’
    

# **3. Choose styled-component over other CSS-in-JS libraries**

Style-Component is one of the most preferred libraries that provides an easy way to use CSS in modern JavaScript. It enables developers to write CSS which is nicely isolated per component while preserving the full power of cascading.

Some pros of using style components are:

-   Gives freedom to build a custom component with CSS
    
-   Enforce the use of props in the place of classes
    
-   Supports server-side rendering with stylesheet rehydration
    
-   Can perform unit testing with Jest Styled Component- A set of utilities to test style components with Jest.
    

# **4. Follow React way to Create separate folders for all files related to each component**

Follow the React way of structuring a React app. A properly maintained folder and file structure help you to understand project flow and simplify code maintenance and extraction to any other project.

Organize files according to components, if there are several small components used by another big component, keep all the related components within that another component folder only and maintain the same hierarchy in the entire project.

For example, the **Form** component has small components such as CSS files, icons, images, tests, and other sub-components all these should be placed in one folder.

# **5. Avoid using Indexes as a Key Props**

According to React document, Key props help react to identify which item has been changed, added, or removed. Therefore, the key should be given to the element inside the array to give the elements a stable identity.

So what will happen if you use indexes as key props?

React uses key props to determine what to render or re-render, as react doesn’t waste time in rerendering duplicates. Thus, when the two elements have the same key one will be omitted by the React.

Another thing to worry about is, React also re-renders elements whose key has changed for a specific element content though the actual content hasn’t been changed.

# **6. Use default props and prop types**

In JavaScript, you can not set the variable and parameter to a particular type. So there is a chance of variable type misinterpretation.

Further, JavaScrip doesn’t allow setting default properties to the objects or components, or to specifying which properties are required and which are optional in React. This will lead to an issue if you forget to assign property to an object or component that is required.

Both the above problem can be solved using prop type and default props. It also helps to improve your code quality making it much safer and faster to test and debug.

# **7. Avoid using props at initial state components**

Using props to generate the initial state component often leads to duplication of “source of truth.” This is because _getInitialstate_ is only invoked once, at the time when the components are first created.

When you make the changes to the props next time on the component, it remains unchanged because the previous value will not be updated. The problem can be solved by avoiding the use of props at the initial state.

# **8. Isolate stateful aspects from rendering**

React components can be stateful or stateless. The stateful components keep track of changing data while the stateless components always render the same data.

To minimize the component complexity it is always a good practice to isolate your stateful data-loading logic from the rendering stateless logic.

# **9. Always follow naming conventions**

Following naming conventions ensures users know how to name digital assets so that they will remain consistent and correct. They help in file organization and management, without naming convention handling code assets can be very difficult.

In react, there are mainly three naming conventions,

1.  The component should be PascalCase
    
2.  Elements that need key should be unique
    
3.  Methods should be written in camelCase and not be application-specific
    

# 10. Write tests for the entire code

Testing ensures code integrity. Therefore it is good practice to create a Test directory within your component’s directory to perform all the required tests and ensure that the addition of new code will not break the existing functionality.

You can perform,

-   Unit Testing to check individual components of React application.
    
-   Integration Testing to check if different pieces of models are working well together.
    
-   End to end testing to check the entire application flow.

# Other react blogs

1.  [Advanced React Roadmap](https://ravisojitra.medium.com/advanced-roadmap-for-react-js-developers-3a40ce4174b9)
    
2.  [React Component Patterns](https://ravisojitra.medium.com/react-component-patterns-805a60b88dba)
    
3.  [Advanced Javascript Design Patterns](https://ravisojitra.medium.com/advanced-javascript-design-patterns-6812f3286585)
    
4.  [State management with Redux toolkit](https://ravisojitra.medium.com/state-management-in-react-with-redux-toolkit-bba750a692d9)