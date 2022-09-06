# React (16.8+)

### React component
```jsx
// Component.jsx
function Component() {
    <div>Component content</div>
}
export default Component();


// Consumer.jsx
import Component from './Component'

function Consumer() {
    <Component />
}
```


### Component state hook
```jsx
// changes button label state when button is clicked
// Component.jsx
import {useState} from 'react'
function Component() {
    const [clicked, setClicked] = useState(false);

    return (
        <button onClick={() => setClicked(true)}>
            {clicked ? "Yey!" : "Nah :("}
        </button>
    )
}
```

### Side effects (va useEffect)
```jsx
// increases counter every second and re-renders it
// Component.jsx
import {useState, useEffect}
function Component() {    
    const [counter, setCounter] = useState(0);

   useEffect( () => {
        const interval = setInterval(() => {
            setCounter(counter+1);
        },1000);
        // cleanup
        return () => clearInterval(interval)
        }
    );

    return (
        <div>{counter}</div>
    )
}