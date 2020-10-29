### React Component
A component is a small, reusable chunk of code that is responsible for one job. That job is often to render some HTML.


import React from 'react';
import ReactDOM from 'react-dom';

class MyComponentClass extends React.Component {
    render(){
        return <h1>Hello world</h1>;
    }
}

ReactDOM.render(
    <MyComponentClass />,
    document.getElementById('app)
);

### React.Component 
JavaScript class. 
To create your own component class

```
class Class_Name extends React.Component {

}
```

### render() method 

A render method is a property whose name is render, and whose value is a function. 

A render method must contain a return statement. Usually, this return statement returns a JSX expression:

```
 render(){
    return // JSX
 }
```

### Multiline JSX 

```
class QuoteMaker extends React.Component {
  render() {
    return (
      <blockquote>
        <p>
          The world is full of objects, more or less interesting; I do not wish to add any more.
        </p>
        <cite>
          <a target="_blank"
            href="https://en.wikipedia.org/wiki/Douglas_Huebler">
            Douglas Huebler
          </a>
        </cite>
      </blockquote>
    );
  }
};

ReactDOM.render(
  <QuoteMaker />,
  document.getElementById('app')
);
```

### Variable Attribute in Component

```
const owl = {
  title: 'Excellent Owl',
  src: 'https://content.codecademy.com/courses/React/react_photo-owl.jpg'
};

// Component class starts here:
class Owl extends React.Component {
  render(){
    return (
      <div>
        <h1>{ owl.title }</h1>
        <img src={owl.src} alt={owl.title} />
      </div>
    );
  }
};

ReactDOM.render(
  <Owl/>,
  document.getElementById('app')
);
```

### Logic in Render 

```
class Random extends React.Component {
  render() {

    const n = Math.floor(Math.random() * 10 + 1);

    return <h1>The number is {n}!</h1>;
  }
}
```

```
const friends = [
  {
    title: "Yummmmmmm",
    src: "https://content.codecademy.com/courses/React/react_photo-monkeyweirdo.jpg"
  },
  {
    title: "Hey Guys!  Wait Up!",
    src: "https://content.codecademy.com/courses/React/react_photo-earnestfrog.jpg"
  },
  {
    title: "Yikes",
    src: "https://content.codecademy.com/courses/React/react_photo-alpaca.jpg"
  }
];

// New component class starts here:
class Friend extends React.Component {
  render(){
    let friend = friends[2]
    return (
      <div>
        <h1>{friend.title}</h1>
        <img src={friend.src} />
      </div>
    );
  }
};


ReactDOM.render(
  <Friend/>,
  document.getElementById('app')
)
```

### Conditional Render

Notice that the if statement is located inside of the render function, but before the return statement. 

```
class TodaysPlan extends React.Component {
  render() {
    let task;
    if (!apocalypse) {
      task = 'learn React.js'
    } else {
      task = 'run around'
    }

    return <h1>Today I am going to {task}!</h1>;
  }
}
```

```
const fiftyFifty = Math.random() < 0.5;

// New component class starts here:
class TonightsPlan extends React.Component{
  render(){
    let result;
    if(fiftyFifty){
      result =  <h1>Tonight I'm going out WOOO</h1>
    } else {
      result = <h1>Tonight I'm going to bed WOOO</h1>
    }
    return result ;
  }
};

ReactDOM.render(
  <TonightsPlan />,
  document.getElementById('app')
);
```

### this component

```
class IceCreamGuy extends React.Component {
  get food() {
    return 'ice cream';
  }

  render() {
    return <h1>I like {this.food}.</h1>;
  }
}
```

```
class MyName extends React.Component {
	// name property goes here:
  get name(){
    return 'whatever-your-name-is-goes-here';
  }

  render() {
    return <h1>My name is {this.name}.</h1>;
  }
}

ReactDOM.render(<MyName />, document.getElementById('app'));
```

### Event Listener

Event handler is a function that gets called in response to an event 
```
render() {
  return (
    <div onHover={myFunc}>
    </div>
  );
}
```

```
class MyClass extends React.Component {
    myFunc(){
        alert('Stop it. Stop hovering.');
    }
    
    render(){
        return (
            <div onHover={this.myFunc}>
            </div>
        )
    }
}
```