# React

### Setup 

```
npm install react react-dom
```

### JSX 

```
const h1 = <h1>Hello world</h1>;
```

```
const myTeam = {
  center: <li>Benzo Walli</li>,
  powerForward: <li>Rasha Loa</li>,
  smallForward: <li>Tayshaun Dasmoto</li>,
  shootingGuard: <li>Colmar Cumberbatch</li>,
  pointGuard: <li>Femi Billon</li>
};
```

> Attributes in JSX

```
const title = <h1 id='title'>Introduction to React.js: Part I</h1>; 
```
```
const panda = <img src='images/panda.jpg' alt='panda' width='500px' height='500px' />;
```

> Nested JSX

```
(
  <a href="https://www.example.com">
    <h1>
      Click me!
    </h1>
  </a>
)
```

> Rendering JSX 

```
ReactDOM.render(
    <h1>Hello world</h1>,
    document.getElementById('app')
);
```

> Variable in ReactDOM.render()

```
const toDolist = (
    <ol>
        <li>Learn React</li>
        <li>Become a Developer </li>
    </ol>
);

ReactDOM.render(
    toDoList,
    document.getElementById('app)
);
```

> class vs className

* in HTML
```
<h1 class="big">Hey</h1>
```

* in JSX
JSX, you can’t use the word class! You have to use className instead
```
<h1 className="big">Hey</h1>
```

* e.g. 
```
// css 
.big {
	font-size: 100px;
}

// js
let myDiv = (
  <div className="big">
    I AM A BIG DIV
  </div>
)

ReactDOM.render(
  myDiv,
  document.getElementById('app')
);

```

> Self closing tags 

JSX, you have to include the slash. If you write a self-closing tag in JSX and forget the slash, you will raise an error

HTML elements such as <img> and <input> use only one tag. The tag that belongs to a single-tag element isn’t an opening tag nor a closing tag; it’s a self-closing tag.

```
<br />

<img />
```

> Javascript in JSX 

```
ReactDOM.render(
  <h1>2 + 3</h1>,
  document.getElementById('app')
);
```