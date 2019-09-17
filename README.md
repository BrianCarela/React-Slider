# React Progress Bar Lab

##### Learning Objectives
* Better understand React's state and props between multiple components
* Practice utilizing ES6 features such as classes, destructuring, and string interpolation
* Successfully build progress bar using React components


##### 1. Setup
* Create a new React app called 'progress_bar'
* Replace the /src/App.css file with the given css styling in this directory
* run `npm start` to run application on localhost 3000
* all of the work in this lab will be done in the `src` folder

##### 2. Build It 
1. App.js
* This component should render an h1 that says "React Progress Bar"
* Add an initial state for this component - { value: 0 }
* Make a function called setValue that accepts a parameter and updates this.state.value with that parameter
* Later, we will be rendering other components within App

2. DisplayProgress Component
* Create a file called `DisplayProgress.js` in the `src` folder.
* This file should have a component class called `DisplayProgress`, which has no state.
* Write a function called getStatus
    * this function takes one argument, `currentValue`
    * it should return 'Complete!' if currentValue = 100
    * otherwise it should return 'In Progress -' along with the currentValue
* Write a function called getStyles
    * this function takes one argument, `percentage`
    * it should return a string accordingly:
        * percentage < 33 - return 'low'
        * percentage > 33 and < 66 - return 'medium'
        * percentage > 66 - return 'high'
* This component should render an h3 that displays the return value of `getStatus` when you pass it the argument of this.props.value
* Later, this component will be rendering another component 

3. ProgressBar Component
* Create a file called `ProgressBar.js`
* This file should have a stateless functional component 
* This component should render..
    * a div with the class 'bar'
    * an inner div with the class equal to this.props.class. This will be determined by the DisplayProgress's getStyles function 
        * styling with the width equal to props.width (It should be `style={{width: `${this.props.width}%`}}`)

4. Slider Component
* Create a file called Slider.js that has a stateless, functional component. 
* This component should just render a html slider (hint - its a kind of input) -
    * min- 0
    * max - 100
    * value - this.props.value 
    * on change - {(e) => this.props.setValue(e.target.value)}

5. Putting it all together
* Have the App component render the DisplayProgress component with the prop `value` equal to this.state.value 
* Have the App component render the Slider component with the prop `value` equal to state.value, and the prop `setValue` equal to this.setValue.bind(this) so that the Slider component has access to the function, and the state on App.js

* Have the DisplayProgress component render the ProgressBar component under the h3. Give it the prop `width` equal to this.props.value and the prop `class` equal to the getStyles function, and pass it the argument of this.props.value 

#### Bonus
* Add proptypes to each component receiving props
* Add some front end validation to ensure the user can't put values in the slider that are 
    * 1 - non-numeric
    * 2 - not less than 0, not greater than 100
