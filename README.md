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

* JSX doesn’t add numbers - it reads them as text, just like HTML.

```
ReactDOM.render(
    <h1>{2 + 3}</h1>,
    document.getElementById('app')
)
```
```
const pi = (
  <div>
    <h1>
      PI, YALL!
    </h1>
    <p>
      {Math.PI.toFixed(20)}
    </p>
  </div>
);

ReactDOM.render(
	pi,
	document.getElementById('app')
);
```

### Variables in JSX 

* access variables while inside of a JSX expression

```
const name = 'Gerdo';

const greeting = <p>Hello, {name}! </p>;
```
```
const theBestString = 'tralalalala i am da best';

ReactDOM.render(<h1>{theBestString}</h1>, document.getElementById('app'));
```

### Variable attributes in JSX 

```
const sideLength = "200px";

const panda = (
  <img 
    src="images/panda.jpg" 
    alt="panda" 
    height={sideLength} 
    width={sideLength} />
);
```

* Object properties are also often used to set attributes

```
const pics = {
  panda: "http://bit.ly/1Tqltv5",
  owl: "http://bit.ly/1XGtkM3",
  owlCat: "http://bit.ly/1Upbczi"
}; 

const panda = (
  <img 
    src={pics.panda} 
    alt="Lazy Panda" />
);

const owl = (
  <img 
    src={pics.owl} 
    alt="Unimpressed Owl" />
);

const owlCat = (
  <img 
    src={pics.owlCat} 
    alt="Ghastly Abomination" />
);
```

e.g.

```
const goose = 'https://content.codecademy.com/courses/React/react_photo-goose.jpg';

// Declare new variable here:
let gooseImg = <img src={goose} />;

ReactDOM.render(
  gooseImg,
  document.getElementById('app')
);
```

### Event Listeners in JSX 

* An event listener attribute’s name should be something like onClick or onMouseOver: the word on, plus the type of event that you’re listening for.

```
function myFunc() {
  alert('Make myFunc the pFunc... omg that was horrible i am so sorry');
}


<img onClick={myFunc} />
```

**Note that in HTML, event listener names are written in all lowercase, such as onclick or onmouseover. In JSX, event listener names are written in camelCase, such as onClick or onMouseOver.**

```
function makeDoggy(e) {
  // Call this extremely useful function on an <img>.
  // The <img> will become a picture of a doggy.
  e.target.setAttribute('src', 'https://content.codecademy.com/courses/React/react_photo-puppy.jpeg');
  e.target.setAttribute('alt', 'doggy');
}

const kitty = (
	<img 
    onClick={makeDoggy}
		src="https://content.codecademy.com/courses/React/react_photo-kitty.jpg" 
		alt="kitty" />
);

ReactDOM.render(kitty, document.getElementById('app'));
```

### If statements 
if and else are not injected in between JSX tags
```
let message;

if (user.age >= drinkingAge) {
  message = (
    <h1>
      Hey, check out this alcoholic beverage!
    </h1>
  );
} else {
  message = (
    <h1>
      Hey, check out these earrings I got at Claire's!
    </h1>
  );
}

ReactDOM.render(
  message, 
  document.getElementById('app')
);
```

e.g.

```
function coinToss() {
  // This function will randomly return either 'heads' or 'tails'.
  return Math.random() < 0.5 ? 'heads' : 'tails';
}

const pics = {
  kitty: 'https://content.codecademy.com/courses/React/react_photo-kitty.jpg',
  doggy: 'https://content.codecademy.com/courses/React/react_photo-puppy.jpeg'
};

let img;

// if/else statement begins here:
if (coinToss() === "heads"){
  img = <img src={pics.kitty} />
} else {
  img = <img src={pics.doggy} />
}

ReactDOM.render(
  img,
  document.getElementById('app')
);
```

### Ternary Operator in JSX 

```
const headline = (
  <h1>
    { age >= drinkingAge ? 'Buy Drink' : 'Do Teen Stuff' }
  </h1>
);
```

```
function coinToss () {
  // Randomly return either 'heads' or 'tails'.
  return Math.random() < 0.5 ? 'heads' : 'tails';
}

const pics = {
  kitty: 'https://content.codecademy.com/courses/React/react_photo-kitty.jpg',
  doggy: 'https://content.codecademy.com/courses/React/react_photo-puppy.jpeg'
};

const img = <img src={pics[coinToss() === "heads" ? "kitty" : "doggy" ]} />;

ReactDOM.render(
	img, 
	document.getElementById('app')
);
```

### JSX Conditionals &&
* && works best in conditionals that will sometimes do an action, but other times do nothing at all.
* If the expression on the left of the && evaluates as true, then the JSX on the right of the && will be rendered. 
* If the first expression is false, however, then the JSX to the right of the && will be ignored and not rendered.

```
const tasty = (
  <ul>
    <li>Applesauce</li>
    { !baby && <li>Pizza</li> }
    { age > 15 && <li>Brussels Sprouts</li> }
    { age > 20 && <li>Oysters</li> }
    { age > 25 && <li>Grappa</li> }
  </ul>
);
```

e.g.

```
const judgmental = Math.random() < 0.5;

const favoriteFoods = (
  <div>
    <h1>My Favorite Foods</h1>
    <ul>
      <li>Sushi Burrito</li>
      <li>Rhubarb Pie</li>
      {!judgmental && <li>Nacho Cheez Straight Out The Jar</li>}
      <li>Broiled Grapefruit</li>
    </ul>
  </div>
);

ReactDOM.render(
	favoriteFoods, 
	document.getElementById('app')
);
```

### .map in JSX 

```
const strings = ['Home', 'Shop', 'About Me'];

const listItems = strings.map(string => <li>{string}</li>);

<ul>{listItems}</ul>
```

e.g.

```
const people = ['Rowe', 'Prevost', 'Gare'];

const peopleLis = people.map(person => 
  <li>{person}</li>
);

// ReactDOM.render goes here:

ReactDOM.render(
  <ul>{peopleLis}</ul>,
  document.getElementById('app')
);
```

### Keys in JSX List 

```
<ul>
  <li key="li-01">Example1</li>
  <li key="li-02">Example2</li>
  <li key="li-03">Example3</li>
</ul>
```
* key is a JSX attribute. The attribute’s name is key. The attribute’s value should be something unique, similar to an id attribute.
* React uses them internally to keep track of lists. If you don’t use keys when you’re supposed to, React might accidentally scramble your list-items into the wrong order.
* A list needs keys if either of the following are true :
    * The list-items have memory from one render to the next. For instance, when a to-do list renders, each item must “remember” whether it was checked off. The items shouldn’t get amnesia when they render.
    * A list’s order might be shuffled. For instance, a list of search results might be shuffled from one render to the next.
    
 e.g.
 
```
const people = ['Rowe', 'Prevost', 'Gare'];

const peopleLis = people.map((person,i) => 
  <li key={'person_' + i}>{person}</li>
);

// ReactDOM.render goes here:

ReactDOM.render(
  <ul>{peopleLis}</ul>,
  document.getElementById('app')
);
```

### React.createElement

* write React code without using JSX 

```
const h1 = <h1>Hello world</h1>;
```
**to**
```
const h1 = React.createElement(
  "h1",
  null,
  "Hello, world"
);
```