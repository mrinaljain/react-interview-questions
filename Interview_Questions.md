<!-- 28 , 55 , 59 , 60 , 68 , 69 , 72 , 74  , 76  , 77 , 78 , 80 84 85 , 89 , 94, 111, 113, 114 , 122 ,124 , 128-->

#### 1. What is React?

React is a Javascript library which makes the DOM manipulation more efficient with the help of Virtual DOM.Also

#### 2. What are the major features of React?

- DOM manipulation is easier becaus of Virtual DOM
- Reusable component makes code more modular and redable
- React can be used even in sub part of a  website 
- Alowes us to create SPA single page applications
- Superpower of variables useState is available

#### 3. What is JSX?

JSX is Javascript XML which is a **syntactic sugar** on top of Javascript which makes it easier to write and create React components which otherwise will be a very long and tedious code in Javascript.
JSX is in background transpiled into the Browres Compatible Javascript with the help of transpiler i.e  **Bable**.
Bable makes sure it transpiles  to browser specific Javascript.

#### 4. What is the difference between Element and Component?

*React Element* is nothing but a Javascript object under the hood this object is Used by react to paint the Virtual DOM and later shift it to the actual DOM of browser.
- React Element are immutable

*React Components* are simple functions that return React Elements.
- React component are statefull, mutable.

#### 5. How to create components in React?

Components in react can be created  in 2 diffrent ways 
   - Class components
   Class components are the old way of creating components where we need to create a class  and extend it by React.component class to get access of methods inside the parent class.
      - we need to use render method to return the react element.
      - We need to use component lifecycle methods to implement sideeffects and other functionalites.

   - Functional Components
   Functional component on the other hand has a new and easy syntax for creating component where we simply define a function by the name of component and return a React Element.
      - React hooks are available to implement sideeffects.


#### 6. When to use a Class Component over a Function Component?

- Legacy code
- Error Boundries

#### 7. What are Pure Components? 

Pure components in React Js as the components which return the same React Element every time based on the same input props .
 - Pure components in class component are implemented by extending purecomponent
 -Pure component in functional component is made by React.memo.


 #### 8. What is state in React?

 State in react is a dynamic container which holds the data on behalf of a component and updates/ re-renders the component in case of any changes inside the data stored in state.
   

 #### 9. What are props in React?

 Props in react are the attributes(read-only inputs) that any component accepts as an input based upon which a component is painted/ rendered.
 - props are immutable.

 #### 10. What is the difference between state and props?

 - state is mutable , props are not
 - props are passed and state can also be pased asprop.
 

#### 11. Why should we not update the state directly?

Because we needs to trigger re-render once state changes and  the inbuilt methods help us to achive that.
otherwise direct state updates might create inconsistancy.


#### 12. What is the purpose of callback function as an argument of setState()?

callback function of the setState is the second argument that runs after the state has ben updated, hence used for the logich to be run after state update.
   - api 
   - action dependent on state update


#### 13. What is the difference between HTML and React event handling?

In HTML the  interaction that happens with the nodees are handeled by addding onclick handelers or attaching the event listeners.
In React thes are handeled by synthetic Events because react BTS takse care of all the browsers and compatibility with single click handeler that we have added.

#### 14. How to bind methods or event handlers in JSX callbacks?

There can be 2 ways for functional components
```
<button onClick={clickEventFunction}>Click Me</button>


let button = useRef();
useEffect(()=>{
button.target.addEventListener(clickEventFunction)
}, [])
```

There can be 2 ways for class components
```
this.method = this.method.bind(this)
```

#### 15. How to pass a parameter to an event handler or callback?

1. this can be done by converting function syntax to arrow function
```
onClick={(parameter)=>functionName()}
```
2. by using the bind method
```
onClick={handleClick.bind(null, 42)}
```

#### 16. What are synthetic events in React?

In React user interaction events are handeled by synthetic Events because react BTS takse care of all the browsers and compatibility with single handeler that we have added.
Example : onClick is replaced by click etc

#### 17. What are inline conditional expressions?

 Terniray , logical AND, logical OR
```
true ?? "statement"

false ?? "statement"

true && "statement"

false && "statement"

true ?? "this":"that"
```

#### 18. What is "key" prop and what is the benefit of using it in arrays of elements?

Key property is usefull in many diffrent ways as it acts as an identity for any element.
- it is passed to parent constructor to initilise the parant element's constructor.
- while deling with Array of elements like in a orderd list , Keys make it easier for the react to update the DOM more efficiently as the React's diffing algorithm can difftentiate the  list items based upon the key's value given that is unique.
- Optimized Reconciliation
- Improves Performance
- Avoids UI mismatch


#### 19. What is the use of refs?
refs in React are  used to store values that can be persisted across re-renders of the element and also whenever there is a change in ref's value it doesnot automatically trigger re-render.
```
useRef // for functional components

c // for class components
```

#### 20. How to create refs?

```
const inputRef = useRef(null);

useEffect(()=>{

   let value = inputRef.current.value;
}, [])

<input type="text" ref={inputRef}>
```
For class component
```
this.inputRef = React.createRef(undefined)
```

#### 21. What are forward refs?

ForwardRef is a Higher order component which is used to recive the useRef values from the parent component and pass it on to the child component.
- so basically we pass useRef value as a prop from parent and iwe can't directly recive it in child so we have to wrap child with a HOC that is ForwardRef component.

#### 22. Which is preferred option with in callback refs and findDOMNode()?
Callback ref basicallay another way to add refs functionality to the DOM element.
   - insted of using useRef hook we can directly provide a callback to the ref parameter .
   ```
   let inputRefCallback = (node) => {
      if (node) {
         node.focus();
      }
   }
   <input type="text" ref={inputRefCallback} >
   ```
**callback refs** are prefered way because
   - doesnot require useeffectto attach
   - direct and fast


#### 23.  Why are String Refs legacy?

Old way of defining refs which is now replaced by useRef and callback refs

#### 24. What is Virtual DOM?

Virtual DOM is a javascript object like structure created by React in order to complete the reconciliation and DOM update process more fficiantly.
   - It is the exact copy of original DOM
   - it contains Js object not Nodes

#### 25. How Virtual DOM works?

Virtual DOM works on the algorthim of react fiber and the entire process is known as reconsiliation.
- react creates a copy of original DOM
- when any state, prop changes then re-render is triggerd
- behind the scenes reach has another tree structure which react compares with the virtual DOM and makes changes in the Virtual DOM
-finally with the help of diffing ALgorithm this changes are shifted to the Orignal DOM in batches.

#### 26.  What is the difference between Shadow DOM and Virtual DOM?

Shadow DOM is a private/protecte DOM inside the Browser DOM which is created by an external element like iframe.
while Virtual DOM is part of the library.


#### 27. What is React Fiber?

React Fiber is the latest reconciliation Algorthim introduced in React 16 which improved the re-rendering process  wit the help of Virtual DOM.
- it also batches similar state updates resulting even lesser DOM interaction.

#### 28. What is the main goal of React Fiber?

- Speed up reconciliation process
- **Incremental Rendering**
 

#### 29. What are controlled components?

Controlled component in react are the ones whos values are controled by the react state variables and 
- they re-render every time state variable changes

#### 30. What are uncontrolled components?

Uncontrolled components in react are the ones who are independent from the react state and there values can be read only using useRef
- no  reender when value changes

#### 31. What is the difference between createElement and cloneElement?

create element creates new elemnt and cloneElement creates a copy of the element where we can change any properties.
```
React.createElement('div', {properties})

React.cloneElement(elementToBeCopied, {newpropeeties/ properties to be overriden})
```

#### 32. What is Lifting State Up in React?

In react there is only unidirectional flow of data is allowed that is from parent to child.
so if there is a case when data of some child is required in some other child in that case the data is defined nearest common ancestor ,  and the data is passed via prop drilling to the bottom. 


#### 33.[TODO] What are the different phases of component lifecycle?
Coponent lifecycle has 2 phases
- Render Phase
- PRe commit phase 
- Commit phase

#### 34. What are the lifecycle methods of React?

badiya jama k likhna hai answer so that i can speak it like a story


#### 35. What are Higher-Order components?

HOC components in react are an wraper arround the react components which unables us to reuse the component by adding some extea functionality on top of it.

HOC takes a component as an input and returns a better version of it without affecting the props .

Setps to create HOC As per defination HOC is acomponent that takes Component and returns modified version of it.
1. Create a Component and take another component as parameter.
2. in the return statement return another component that is basicaly a function in simple language.
3. pass the props recived from HOC down to child Component.
```

function HOC(Component) {
  
   return (props)=> (
      <>
         <div>Modification</div>
         <Component {...props}/>
      </>
      
   )
}
```


#### 36. How to create props proxy for HOC component?

**Prop proxy** for HOC means adding new props in between while orignal props of components are being passed to the component.

```
function HOC(Component){

return (props)=>{
   let newProps = {
      naem: "dsad",
      clASS" "SADAS"
   }
   <>
   <div> Modification </>
   <Component {...newProps} {... props}/>
   </>
 } 
}

```

#### 37. What is context?

Context is a storage container/ shared global state in form of an Object , which acts as a common storage and single source of truth to all the childrens who are subscribed to its values.
- it saves prop drilling

```
let {Provider, Consumer} = React.createContext({})
```
- in class components where useContext Hook is not available then Consumer can be used as alternative


#### 38. What is children prop?

Children prop is basicaly passing JSX elements to another component via putting them between opening and clossing tags.. and then accesing it as children attribute  in next widget
```
<ParentComponent props={props}>{jsx eements}</ParentComponent>


function ChildComponent({props,children})=>{

   return (
      <div>
       {childern}
      </div>
   )
}
```

#### 39. How to write comments in React?

- /* */
- //


#### 40. What is the purpose of using super constructor with props argument?

in React Class copmonent using super(props)  does following
- It takes the props and passes it to parent's constructor
- the parent(React.component) constructor takes the props and assignes it to this.props
- now this.props is available to use across the component and also in diffrent lifecycle methods.


#### 41. What is reconciliation?

When a component's props or state change, React decides whether an actual DOM update is necessary by comparing the newly returned element with the previously rendered one. When they are not equal, React will update the DOM. This process is
called **reconciliation**.


#### 42. How to set state with a dynamic key name?
dd
```
this.setState({ [event.target.id]: event.target.value })

[event.target.id] is baacically the dynamic part
```

#### 43. What would be the common mistake of function being called every time the component renders?

Common mistakes
 - dependency array might not be passed in useEffect.
 - useCallback hook is not being used
 - wrong assigning of function to handler
  ``` return <button onClick={this.handleClick()}>{'Click Me'}</button>```


#### 44. Is lazy function supports named exports?

lklk

#### 45. Why React uses className over class attribute?

React is built on top of Javascript and in javascript OOPs the Class is a protectected keyword, hence it is not used in Jsx syntax to avoid conflicts

#### 46. What are fragments?

Fragments are the element wrapers which allow us to enclose  around html elements to give a group  one common wrapper.


#### 47. Why fragments are better than container divs?

Fragments are better as they dont showup on DOM as a node and yet allow us to group HTML elements.
- Faster
- less space

#### 48. What are portals in React?

A React Portal provides a way to render a child component into a different part of the DOM rather than inside its parent component’s DOM hierarchy.

```
React.createPortal("Element", targetDiv, key)
```

#### 49. What are stateless components?

Stateless components in react are the ones who does not have their own state object and they are dependent o the props recived from the parent element vie prop drilling.

#### 50. What are stateful components?

Statefull components in React are the ones who maintain there own state , either be it a class component using state object or functional component using the useState hook.

#### 51. How to apply validation on props in React?

validation can be appliud using proptypes
```
DefaultPropsChild.propTypes = {
   name: PropTypes.string.isRequired,
   job: PropTypes.string.isRequired,
}
```

proptypes are depricated in latest react version as React is promoting use of typescript which is typesafe by default.

#### 52. What are the advantages of React?

- Less interaction with DOM
- Modular code
- Components available
- Browser compatibility with JSX, synthetic events
- Easy to write test cases, unit tests.


#### 53. What are the limitations of React?

- Doesnot support SEO as most content renders on browser .
- heavy bundle size
- React learning curve.


#### 54. What are error boundaries in React v16?

Error boundries in React are created with the help of a lifecycle hook in react componentDidCaatch.
So basically we wrap the component with class component and check if there is an errr
```


```

#### 55. How are error boundaries handled in React v15?

How are error boundaries handled in React v15?
Back to Top
React v15 provided very basic support for error boundaries using unstable_handleError method. It has been renamed to componentDidCatch in React v16.


#### 56. What are the recommended ways for static type checking?

type checking can be implemented using type script Or by implementing defaultype proptype in  component.


#### 57. What is the use of react-dom package?

React is a frontend library that can work on diffrent platforms and environmemnts like web and mobile etc.
React DOM package helps to render/connect the react functionality on the browser.
- like defining the root element
- rendering the jsx element

#### 58. What is the purpose of render method of react-dom ?

render method of react-dom is used to convert the js object which is returned by react which we call a react element into a DOM nod and render it on browser. 


#### 59. What is ReactDOMServer?

ReactDOMServer is the server for handeling 


#### 60. How to use innerHTML in React?

in React inner HTML can be replaced by {} and calling a react component to fill that space with th eElement.

```
let htmlElelemt ={
   _html: "<div> Dangerously set</div> "
}

render(){

   return <>
      <div dangerouslySetInnerHTML={htmlElelemt}></div>
   </>
}
```

#### 61.  How to use styles in React?

styles in react can be used in 3 ways 
- inline style where we can directly add style tag to element in JSX and write css styles in camelCase.
- other way is to create an objext with key value pairs in which key is property name and value is the css value , and later on pass object to the element;s style property.

#### 62. How events are different in React?

Events in react are synthetic , because react adds a wraper on top of regular DOM elements
- click becomes OnClick
this is done to maintain consistency and provide support for diffrent browsersBTS.

#### 63. What will happen if you use setState() in constructor?

 Can't call setState on a component that is not yet mounted.
 kyu hi SetState call krna hai constructor mai, jo bhi value change kr reha o direct constructor mai hi assign kr do na.


#### 64. What is the impact of indexes as keys?

index as a keys are anti-pattern, because index  does not give gurante of uniqueness and also it can change based upon item removal or insertion.
this can create issues during rerenders because React highly depends on keys during the reconciliation process.

#### 65. Is it good to use setState() in componentWillMount() method?

component will mount is the lifecycly hook that runs just before render hence we can use it for some specific purposes like calculating width , height of sceen etc
BUT ITS NOT RECOMENDED

#### 66. What will happen if you use props in initial state?

using props in initial state state will work fine but 
- prop value will not update because constructor only runs one time
- better to use props outside , directly


#### 67. How do you conditionally render components?

We can use Logical operators like ?? or &&  or Ternirroy operator


#### 68. Why we need to be careful when spreading props on DOM elements?


#### 69. How you use decorators in React?

#### 70. How do you memoize a component?

in react we can memoize a component by passing it to another Higher order component known as React.memo right before exporting it 

export default React.memo(Component)
- it useses the shallow comparision which is less reliable.

#### 71. How you implement Server Side Rendering or SSR?

In react SSR can be implemented using ReactDOMServer
- it converts React component into HTML string template 
- the html string is further sent to user
- this under goed dehydration which adds interactivity to the code.
- following methods are available to be used
   - renderToString
   - renderToStaticMarkup
   - renderReadablestream
   - renderToPipableStream

#### 72. How to enable production mode in React?



#### 73. What is CRA and its benefits?

CRA is  create react app and it is npm plugin which creates a initial react project with well definde folder structure  
 - also pre adds important things like package bundler like bable 
 - gives initial configuration file as package.json
 - zero configurayion


#### 74. What is the lifecycle methods order in mounting?

- constructor
- componentWillMount
- render
- copmonentDidMount


#### 75. What are the lifecycle methods going to be deprecated in React v16?

- componentWillMount
- componentWillUpdate
- componentWillReceiveProps


#### 76. What is the purpose of getDerivedStateFromProps() lifecycle method?

The purpose of get derived state from props


#### 77. What is the purpose of getSnapshotBeforeUpdate() lifecycle method?


#### 78. Do Hooks replace render props and higher order components?


#### 79. What is the recommended way for naming components?

Recomended way of naming components in react is the camelcase with first letter capital.
- also knone as pascle case or uppercamelcase
- name of component and name of file should be same


#### 80. What is the recommended ordering of methods in component
class?

i. static methods
ii. constructor()
iii. getChildContext()
iv. componentWillMount()
v. componentDidMount()
vi. componentWillReceiveProps()
vii. shouldComponentUpdate()
viii. componentWillUpdate()
ix. componentDidUpdate()
x. componentWillUnmount()
xi. click handlers or event handlers like onClickSubmit() or onChangeDescription()
xii. getter methods for render like getSelectReason() or getFooterContent()
xiii. optional render methods like renderNavigation() or renderProfilePicture()
xiv. render()


#### 81. What is a switching component?

Switching component is a component which handels multiple components and rendesd on based on props value
```
const PAGES = {
  home: HomePage,
  about: AboutPage,
  services: ServicesPage,
  contact: ContactPage
}
const Page = (props) => {
  const Handler = PAGES[props.page] || ContactPage
  return <Handler {...props} />
}
```

#### 82. Why we need to pass a function to setState()? || Why function is preferred over object for setState() ?

setstate can take direct value of state object as well , but providing function gives us access to the previous value of state object which helps us in updating value asyncly.

#### 83. What is strict mode in React?

Strict mode in react puts some extra checks and debuging levels for the developement phase.
- it runs stateUpdates twice just to be sure
- warns about deperecated methods

#### 84.  What are React Mixins?[deprecated]

React mixins acts as a universal functionalites that can be added as an extra addon to any components.

#### 85. Why is isMounted() an anti-pattern and what is the proper
solution?



#### 86. What are the Pointer Events supported in React?

Here are the common pointer events supported in React:

onPointerDown: Triggered when the pointer is pressed down (similar to mousedown).

onPointerUp: Triggered when the pointer is released (similar to mouseup).

onPointerMove: Triggered when the pointer is moved across the screen.

onPointerEnter: Triggered when the pointer enters the element (similar to mouseenter).

onPointerLeave: Triggered when the pointer leaves the element (similar to mouseleave).

onPointerOver: Triggered when the pointer moves over the element (similar to mouseover).

onPointerOut: Triggered when the pointer moves out of the element (similar to mouseout).

onPointerCancel: Triggered when a pointer event is canceled, like when a touch event is interrupted.

onPointerMove: Similar to onMouseMove, it's triggered when a pointer is moved across an element.


#### 87. Why should component names start with capital letter?

- because lowercase ko React DOM eement samaj leta hai


#### 88. Are custom DOM attributes supported in React v16?

YES

#### 89. What is the difference between constructor and getInitialState?[deprecated]

constructor initiliases the class and  sets the values yo the current class.


#### 90. Can you force a component to re-render without calling setState?

- **forceUpdate** in class component
- updating key in functionalcomponent also triggers rerender
- useReducer

#### 91. What is the difference between super() and super(props) in React using ES6 classes?

super method is useed to initilise the parent constructor of the clasee
- super(props) sends props to the parent constructor and the parent constrictor sets props to this.props which makes it available across the components
- this also binds props changes with lifecycke hooks


#### 92.  How to loop inside JSX?

by using javascript syntax with the help of curly brackets
```
{map.forEach(callback)}
{map.map(callback)}
```

#### 93. How do you access props in attribute quotes?

But you can put any JS expression inside curly braces as the entire attribute value. So
the below expression works:
     ```<img className='image' src={'images/' + this.props.image} />```
Using template strings will also work:
    ``` <img className='image' src={`images/${this.props.image}`} />```


#### 94. What is React proptype array with shape?


#### 95. How to conditionally apply class attributes?


```
<div className={`classname1` ${true ? "this" : "orThis"}} > conent</div>

OR
<div className={'btn-panel ' + (this.props.visible ? 'show' : 'hidden')}>
```

#### 96. What is the difference between React and ReactDOM?

React package is used for all state managemant and comparision purposes

ReactDOM package is used for final interaction with DOM


#### 97. Why ReactDOM is separated from React?

because React is alibrary that can support diffrent environments other then browser so in that case react dome k alava kuch aur use kr sakte hai.

#### How to use React label element?

Since for is a reserved keyword in JavaScript, use htmlFor instead.

```
       <label htmlFor={'user'}>{'User'}</label>
       <input type={'text'} id={'user'} />
```


#### 99. How to combine multiple inline style objects?

using spread operator in one compn object


#### 100. How to re-render the view when the browser is resized?

You can listen to the resize event in componentDidMount() and then update the dimensions ( width and height ).


#### 101. What is the difference between setState() and replaceState() methods?

When you use setState() the current and previous states are merged.
replaceState() throws out the current state, and replaces it with only what you
provide


#### 102. How to listen to state changes?

The componentDidUpdate lifecycle method will be called when state changes. You can
compare provided state and props values with current state and props to determine if
something meaningful changed.
      ``` componentDidUpdate(object prevProps, object prevState)```


#### 103. What is the recommended approach of removing an array element in React state?

access previous state then using filter method remove and return new state


#### 104. Is it possible to use React without rendering HTML?

yes just return nothing in component



#### 105. How to pretty print JSON with React?

 We can use <pre> tag so that the formatting of the JSON.stringify() is retained:



#### 106.  Why you can't update props in React?
Its not like you can't , pr nhi krna chahiye kyuki react ke unidirectional flow ka samman krna chahiye


#### 107. How to focus an input element on page load?

using useref hook
- either use the functional approach
- or use the componentDidMount approach



#### 108. What are the possible ways of updating objects in state?

possible ways
- direct new state object pass ker do
- ya to callback function use kro usme prev object k base pr update kro

#### 110 . How can we find the version of React at runtime in the browser?

```
const REACT_VERSION = React.version
```

#### 111. What are the approaches to include polyfills in your create-react-app ?


#### 112. How to use https instead of http in create-react-app.

for parcel we can add --https flaf 

for creat react app You just need to use HTTPS=true configuration. You can edit your package.json scripts
section:
```
"scripts": {
         "start": "set HTTPS=true && react-scripts start"
}
```
or just run set HTTPS=true && npm start


#### 113. How to avoid using relative path imports in create-react-app?

```
```

#### 114. How to add Google Analytics for React Router?

#### 115. How to update a component every second?

using a ticker in useeffect


#### 116. How do you apply vendor prefixes to inline styles in React?

automatic => camlecase


#### 117. How to import and export components using React and ES6?

```
export default class MyProfile extends React.Component {
render(){
           return (
             <User type="customer">
             </User>
               //...
)
}
}
```

#### 119. Why is a component constructor called only once?

in order to initilise the values passed as parameter and to call parent class constructor.
- It gets called when the component is created but not when it re-renders due to state or prop updatesIt gets called when the component is created but not when it re-renders due to state or prop updates


#### 120. How to define constants in React?

for class component use static keyword
for functional component use const


#### 121. How to programmatically trigger click event in React?

using useRef .current
```
i. Create ref in render method:
           <input ref={input => this.inputElement = input} />
ii. Apply click event in your event handler:
           this.inputElement.click()
```

#### 122. Is it possible to use async/await in plain React?



#### 123. What are the common folder structures for React?

feature , component , css
file type wise


#### 124. What are the popular packages for animation?


#### 125. What is the benefit of styles modules?

it helps to maintain isolation of css properties


#### 126. What are the popular React-specific linters?

ESlint


#### 127. How to make AJAX call and in which component lifecycle methods should I make an AJAX call?

```
componentDidMount() {
           fetch('https://api.example.com/items')
             .then(res => res.json())
.then(
               (result) => {
                 this.setState({
                  employees: this.employees
                  })
               })
               }
```


#### 128. What are render props?

Render Props is a simple technique for sharing code between components using a prop whose value is a function. 
The below component uses render prop which returns a  React element.

```
<myComponent render={(parameter)=>{console.log("")}}>
```

## React Router

#### 129. What is React Router?

React router  is a routing library available on top of react framework which alows us to define the routing logic 


#### 130. How React Router is different from history library?

It is a wrapper around history library,  But React Router does the extra job of:

- mapping paths to components,

- managing route state,

- rendering different views based on the URL.


#### 131 What are the <Router> components of React Router v4?



## React Internationalization


## React Testing

## React Redux


## React Native

## React supported libraries & Integration

## Miscellaneous

#### 206.[TODO] What are the main features of Reselect library?

#### 207.[TODO] Give an example of Reselect usage?

#### 209.Does the statics object work with ES6 classes in React?

yes static objects can be created to declare  a property on the class itself , so we donot require an instance of class to access it.


#### 210.  Can Redux only be used with React?

Redux is a state management paridgim and it is  not limited to any library , hence it can be implements with other programing languages also if followed the similar structure of container, slice , selector, action and dispatcher.

#### 211. Do you need to have a particular build tool to use Redux?

No Redux is a plain Javascript library so its not required.

#### 212.[TODO] How Redux Form initialValues get updated from state?

initial values can be either defined at the time of creating store , wile defining slices.
For updatingth state we can define reducer functions which can be handeled on the based of a dispatched action.

#### 213.  How React PropTypes allow different types for one prop?

We can use proptype.any while defining

```
age: PropTypes.oneOfType([PropTypes.string, PropTypes, number])
```

#### 214.  Can I import an SVG file as react component?

YEs If we pass it in render

```
       import { ReactComponent as Logo } from './logo.svg'
```

#### 215. [TODO] Why are inline ref callbacks or functions not recommended?

because 


#### 216. What is render hijacking in react?

render hijack means k when you decide that whats gonna renderd by component from outside or an HOC.


#### 217. [TODO]What are HOC factory implementations?


#### 218. How to pass numbers to React component?

```
<div num={34}></div>
```

#### 219.[TODO]

#### 220.[TODO] What is the purpose of registerServiceWorker in React?

#### 221. What is React memo function?

React memo function is one of the optimization techniques for the react web app.
Memo function is a higher order function which wraps arround a component and prevents the rerendering of the component untill and unless any props or state inside child has changed.
- performs a shallow comparison of its props 

#### 222. What is React lazy function?

Lazy function is used to load or import a route asynchronously only when it is requested by user i.e when user visits that route
- not to forget suspense for loading
```
const OtherComponent = React.lazy(() => import('./OtherComponent'));
```

#### 223. How to prevent unnecessary updates using setState?

- we can use the functional approach where we can check if prev state is equal to current valus then we can abort update.
- we can batch multiple updates in single setstate
- use react memo to avoid faltu rendering

#### 224. How do you render Array, Strings and Numbers in React 16 Version?

we can render arrys using a map method in between curly braces
we can directly remder string and number using there value given by useState hook
- another way is to return mixed array 
```
function MixedArrayExample() {
  const items = ['Apple', 'Banana', 'Orange'];

  return [
    <h1 key="header">Fruits List:</h1>,
    ...items.map((item, index) => <li key={index}>{item}</li>),
    'End of list',
    42,  // A number rendered directly
  ];
}
```

#### 225 [todo]How to use class field declarations syntax in React classes?

#### 226. What are hooks?

Hooks in react are functions with superpowers of react.
Hooks contain a functionality which can be seperated as a service 
hooks have anomenclature of useHookname

#### 227. What rules need to be followed for hooks?
- naming convention should be starting from use
- it should return or it can be empty 
-  call hooks from toplevel only
- do not call hooks from javascript


#### 228. How to ensure hooks followed the rules in your project?

use eslint plugin for hooks

#### 229.[TODO] What are the differences between Flux and Redux?

flux is a programing paridigm on whicg redux works


#### 230 [TODO] What are the benefits of React Router V4?

#### 231. Can you describe about componentDidCatch lifecycle method signature?

ComponentDidCatch lifecycle method is part of the error lifecycle of a react component.
It is used to create error boundries across the class components by wrapping class components as a children prop inside a error boundry component.
This automatically detects error and informs us to take action accordingly.
```
componentDidCatch(error, info)

```

#### 232. In which scenarios error boundaries do not catch errors?

- when error is in itself
- when the code is async
- when error inside event handelers


#### 233. Why do you not need error boundaries for event handlers?

because eventhandlers does not affect first render / mounting .
so they can be managed later by try/catch block.

#### 234. [TODO]What is the difference between try catch block and error boundaries?


#### 235. What is the behavior of uncaught errors in react 16?

whole componnent will be unmounted. basically it follows Atomicity


#### 236. What is the proper placement for error boundaries?

- on top of the parent component screen
- or wrap every screen individually


#### 237. What is the benefit of component stack trace from error boundary?

used to track path of the error causing component

#### 238. What is the required method to be defined for a class component?

renderis required

#### 239. What are the possible return types of render method?

- it can return JSX
- it can return Array of elements
- portals
- string 

#### 240. What is the main purpose of constructor?

main purpose is to initialise the  props provided by parent inside  this .props which is present inside parent class
- also defines any local state if required.

#### 241. Is it mandatory to define constructor for React component?

No if not needed then do not define constructor.

#### 242. What are default props?

default props are the values if no props are passed from parent .

```
MyButton.defaultProps = {   
   color: 'red' 
   };

```

#### 243. Why should not call setState in componentWillUnmount?

the setState method triggers rerender of the component , while componentWillUnmount is called just before unMount so there is a possibility that setstate will run but component will be unmounted till then.

#### 244. [TODO] What is the purpose of getDerivedStateFromError?

#### 245. [TODO]What is the methods order when component re-rendered?


- getDerivedStateFromProps
- shouldComponentUpdate
- render
- getSnapshotBeforeUpdate
- componentDidUpdate