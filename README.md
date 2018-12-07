# presentation-react.github.io
# Transcript of pesentation

What’s React?

React is a JavaScript library for building user interfaces. It is maintained by Facebook and a community of individual developers and companies. 
React can be used as a base in the development of single-page or mobile applications. Complex React applications usually require the use of additional libraries for state management, routing, and interaction with an API. 

A little history

React was created by Jordan Walke, a software engineer at Facebook. He was influenced by XHP, an HTML component framework for PHP
 It was open-sourced at JSConf US in May 2013.
On April 18, 2017, Facebook announced React Fiber, a new core algorithm of React framework library for building user interfaces. 

Basic usage

In the picture you can see the Greeter class is a React component that accepts a property greeting. The ReactDOM.render method creates an instance of the Greeter component, sets the greeting property to 'Hello World' and inserts the rendered component as a child element to the DOM element with id myReactApp.
When displayed in a web browser the result will be
Concepts of React 
1.  Elements and components
Elements are JavaScript objects that represent HTML elements. They do not exist in the browser. They describe DOM elements like h1, div, or section.

Components are React elements written by the developer. Usually these are parts of the user interface that contain their structure and functionality. For example, such as NavBar, LikeButton, or ImageUploader.
In the picture you can see instances of  elements and components React.

2. Properties

Properties can be understood as component options. They are provided as component arguments and look the same as HTML attributes.
In the picture in the render function, the Photo component has 2 properties: imageURL and caption.
Inside the custom render function, the imageURL property is used as the src for the image. The caption property is used as the text of the span element. 
It is worth noting that the properties of the component are immutable. If the component has mutable properties, use the state.

3. JSX

JSX is a technique for creating React elements and components. For example, this is a React element written in JSX:
The same element can be written in JavaScript:
Since JSX requires much less effort, it transforms into JavaScript before running in a browser.

4. Virtual DOM

Virtual DOM is a tree of React elements on JavaScript. React renders the Virtual DOM in the browser to make the interface visible. React monitors changes in Virtual DOM and automatically changes the DOM in the browser so that it matches the virtual one.
React creates an in-memory data structure cache, computes the resulting differences, and then updates the browser's displayed DOM efficiently. This allows the programmer to write code as if the entire page is rendered on each change, while the React libraries only render subcomponents that actually change.

React Props

Passing only props from component to component doesn’t make the component interactive, because nothing is there to change the props. Props are read-only. That’s the time when React state comes into play which can be changed. The state is co-located to a React component.
The figures shows examples of props that you can use.

State

As I said before, to change the state of a component you must use state. A state is a special object inside a component. It stores data that may change over time.
In the picture the component has a new function getInitialState. React calls it after initializing the component. It sets the initial state (which implies the name of the function).
The component also has a toggleLiked function. Using the setState function, it switches the liked state. The event is suspended by a button

Here is what happens after the component is drawn:
- After pressing the button, toggleLiked is called.
- Like state changes
- React redraws a component in Virtual DOM
- New Virtual DOM is compared with the previous one.
- React isolates changes and updates them in the browser DOM
In this case, React will change the class name of the button.

Refs

Refs are used to get a reference to a DOM (Document Object Model) node or component in React.
Refs are created using React.createRef() and attached to React elements via the refattribute.
When to Use Refs.
There are a few good use cases for refs:
-	Managing focus, text selection, or media playback.
-	Triggering imperative animations.
-	Integrating with third-party DOM libraries.
Avoid using refs for anything that can be done declaratively.

Render

First of all, the virtual element (element, or React component) is rendered. Remember, while the virtual element is only in javascript memory. We must explicitly tell React to draw it in the browser.
The rendering function takes two arguments: a virtual element and a real DOM node. React takes a virtual item and adds it to the specified node. Now the image can be seen in the browser.

Component life cycles

A component has a life cycle that is divided into phases. The figure shows the life cycle phases:

componentWillMount - the component will be mounted. At the moment we have no opportunity to see DOM elements.

componentDidMount - the component was mounted. At the moment, we have the opportunity to use refs, and therefore this is the place where we would like to indicate the focus setting. Also, timeouts, ajax requests and interaction with other libraries should be handled here.

componentWillReceiveProps - the component receives new props. This method is not called at the time of the first render.

shouldComponentUpdate - should the component be updated? In fact, usually the reactor itself perfectly understands. But sometimes manual control can significantly speed up the work in "bottlenecks". With this method you need to work very carefully.

componentWillUpdate - called right before render when new props and state are received. You cannot call setState in this method.

componentDidUpdate - called immediately after render. It is not called at the time of the first render of the component.

componentWillUnmount is called immediately before the component is removed from the DOM.

Advantages of using React

1. Performance when used correctly (speed).
2. You can always tell how your component will be drawn by looking at the source code.
3. Linking JavaScript and HTML in JSX makes components easy to understand.
4. You can render React on the server.
5. Thanks to the reuse of the code, it has become much easier to create mobile applications (extensibility).

Compare

In the picture you can compare how React works
