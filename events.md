# Events
How to handle events and what's happening behind the scenes. 

## Event Handler Design
### Polling
<b>Pattern 1:</b> Periodically check the state of a variable (ex. a key)

<b>Pattern 2:</b> Periodically check the contents of a data structure (ex. a queue) for state changes. When a variable's state changes (ex. keypress), record that state change in the data structure.

The disadvantage is that our application needs to keep checking the state or data structure. This adds lots of overhead as the number of variables increases, and we can never get continuous state checking.

### Interrupting
<b>Pattern:</b> Bind an "event handler" to an object (ex. a DOM element) that executes a script or function when a hardware interrupt (ex. keypress) occurs. The handler is passive -- it does not do anything unless the hardware interrupt occurs. 


## Event Handler Implementation
### HTML event handlers
```javascript
<button onclick={handleClick()}>
  // Click me
</button> 
```

### Vanilla JS event handlers
```javascript
<button>Click me</button>
<script>
  let button = document.querySelector("button"); 
  button.addEventListener("click", () => { // Bind event handler to button
    // Do stuff
  });
</script>
```

### React event handlers
In React, we pass the function name into a component's prop. When we click on the component, the function fires. 
```javascript
// Good: Event handler triggers when we click on the button
<button onClick={handleClick}>
  Click me
</button>
```

However, avoid this common pitfall where we call the function within the component prop. 
```javascript
// Bad: Event handler triggers when the component renders, because we're calling the function in the prop. 
// This looks similar to the HTML event handler, except we use 'onClick' instead of 'onclick'. 
<button onClick={handleClick()}
  Click me
</button>
```

