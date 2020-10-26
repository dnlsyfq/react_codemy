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

