
# <u>Week 1</u>
- #### Review of MAD 1
	- Components of an App: 
		- Backend - store data, process logic, relation between data elements
		- Frontend - User-facing view, abstract for machine interaction
		- naturally implies a client-server architecture
- Advanced Frontend development
	- Exploring JavaScript and how to use it
	- JavaScript, APIs, Markup — the JAMStack
	- VueJS as a candidate frontend framework
- Other topics
	- asynchronous messaging, Email
	- Mobile/Standalone apps, PWA (Progressive Web App)/SPA (Single Page App)
	- Performance measurement, benchmarking, optimisation
	- Alternative to REST

- ## JavaScript
	- ##### Origins
		- created as a scripting language for Netscape Navigator
		- intended as 'glue' language — stick modules from other languages together
		- primarily meant to assist "applets" in Java
		- Issues: Slow and limited capability
	- Power
		-  Google Maps — pan around map, zoom in/out seamlessly - fluid user interface: Load only what is needed
		- Described and names AJAX (Asynchronous Javascript and XML) by James Garrett (2005)
		- Allowed true 'web applications' that behave like desktop applications
		- evolved considerably since then
	- Standardisation
		- ECMA (European Computer Manufacturers Association) — standard 262
		- subsequently called ECMAScript
		- Significant changes in ES6 — 2015
			- yearly releases since then
			- 'feature readiness' oriented approach
	- Which version to use
		- ES6 has most features of modern languages
		- possible approaches if the language does not work on an older browser:
			- ignore old browser
			- package browser along with application — useful for limited access
			- Polyfills: include libraries that emulate newer functionality for older browsers
			- Compilers: BabelJS — convert new code to older compatible versions
	- Implications of JS Origins
		- ease of use given priority over performance
		- highly tolerant of errors — fail silently
			- Debugging difficult!
			- Strict mode: "use strict";
		- Ambiguous syntax variants
			- Automatic semicolon insertion
			- Object literals vs Code blocks use "{}" notation
			- Function: statement or expression? Impacts parsing
		- Tools called <u>Linters</u>: goes through your source code and gives you a solution on how to improve the readability and maintainability of the code
		- Limited IO support: errors "logged" to "console"
		- Closely integrates with presentation layer: DOM APIs
		- Asynchronous processing and the Event Loop — very powerful!
	- Using JS
		- Not originally meant for direct scripting
			- Usually not run from command line like Python for instance
		- Need HTML file to load the JS as a script
			- Requires browser to serve the files
			- Links and script tags etc.
			- *May* not directly work when loaded as a file
		- NodeJS allows execution from command line
	- **DOM**
		- Document Object Model
			- Structure of the document as shown on the browser
		- can be manipulated through JS APIs
		- One of the most powerful aspects of JavaScript
		- <u>Input</u>: clicks, textboxes, mouseover,...
		- <u>Output</u>: test, colours/styles, drawing,...

- ## JavaScript Syntax
	- #### Basic Frontend Usage
		- Frontend JavaScript: must be invoked from HTML page
			- will not execute if loaded directly
		- Scripting language – no compilation step
		- Loosely structured – no specific header, body, etc.
	- #### Identifiers
		- Reserved words:
			```js
			await break case catch const continue debugger default delete do else export extends finally for function if import in instanceof let new return static super switch this throw try typeof var void while with yield
			```
		- Literals (values)
			```js
			true false null
			```
		- Other to avoid
			```js
			enum implements package protected interface private public Infinity NaN undefined async
			```
	- #### Statements and Expressions
		- Statement
			- piece of code that can be executed
			- standalone operation or a side effect
			```js
			if (...) {
				// do something
			}
			```
		- Expression
			- piece of code that can be executed to obtain a value to be returned
			- anywhere you need a 'value' – function argument, math expression, etc.
			```js
			x=10;
			"Hello world"
			```
	- #### Data Types
		- Primitive data types: built into the language
			- undefined, null, boolean, number, string (+bigint, symbol)
		- Objects
			- compound pieces of data
		- Functions
			- Can be handled like objects
			- Objects can have functions: methods
			- Functions can have objects??

- ### Identifiers, Expressions, and Variables
	```js
	console.log("Hello console!");
	
	/* multi
	line 
	comment */
	
	// Identifiers and Variables
	let x = 0;
	const  AnotherVariable = 42;
	var we_dont_use_var = true;
	
	// console.log(AnotherVariable)
	
	// Scope - where is the variable visible
	var x1 = 10;
	let x11 = 11;
	const x12 = 12;
	{   
	    console.log(x11);
	    var x2 = 30;
	    let x21 = 31;
	    const x22 = 32;
	}
	
	console.log(x2);
	console.log(x12); // this will be problematic becuase 'let' allows you to have more restrictive scope
	console.log(x22); // again will not work because 'const' gives block-level scope
	// const cannot have its value changed
	
	// Strings
	let s = "Hello";
	console.log(s);
	console.log(s.length);
	console.log(s[0]);
	console.log(s.substring(2,4));
	
	// Templates
	let st = `${s} World`; // Any string that starts/ends with backward quote = template string
	console.log(st);
	console.log(`Length of ${st} = ${st.length}`);
	
	// Operators
	console.log(3 + 4);
	console.log('3' + '4');
	console.log('3' + 4); // --> coercion: converts both into the same type
	console.log('3' * '4'); //  will convert both into numbers and print '12'
	// Loose and string equality
	console.log(3 == 4); // False
	console.log(3 == 3); // True
	console.log(3 == '3'); // True -- because JS will convert into same datatype
	console.log(3 === '3'); // False -- Strict equality
	console.log(undefined == null); // True
	console.log(undefined === null); // False
	```

- ## Control Flow and Functions
	- Non-Values
		- undefined
			- usually implies not initialised
			- default unknown state
		- null
			- Explicitly set to a non-value
	- `const`: declares an immutable object
	- `let`: variable can be updated
	- Control Flow
		- Conditional execution: `if` , `else`
		- Iterations: `for` , `while`
		- Change in flow: `break` , `continue`
		- Choice: `switch`
	- Functions
		- reusable block of code; can take parameters/arguments and perform computation
		- functions are themselves objects that can be assigned
		- Function Notations differ
	```js
	// CONDITIONS
	let x = 3;
	if (x==5) {
		console.log("What??");
	} else {
		condole.log("Of course 3 != 5");
	}
	
	
	// ITERATION
	for (const x=0; x<5; x++) {
		console.log(x);
	} // Will not run because x is const
	for (let x=0; x<5; x++) {
		console.log(x);
	}
	const v = [1,2,3,4];
	for (const x in v) {
		console.log(x);
	} // when using 'in' x doesn't take the values of v, but takes the index values
	for (const x of v) {
		console.log(x);
	} // this will the give the values of v
	
	
	// FUNCTIONS
	function add1(x,y) {
		return x + y;
	} // Statement; doesn't return anything, whatever it returns goes into 'add'
	console.log(typeof(add1));
	console.log(add1(3,4));
	add1.v = {'a':3, 'b':6};
	console.log(add1.v);
	console.log(add1.v.b);
	
	let add2 = function(x,y) {
		return x + y;
	} // Named expression
	
	let add3 = (x,y) => x + y; // Arrow function; best suited for only simple functions
	
	console.log(function(x,y) {return x+y;} (2,3)) // Immediately invoked func
	
	let x = function () {return "hello"}; // Anonymous bound
	(function() {return "hello"} ()); // Declare a function and invoke; IIFE (avoid these)
	```

- ### DOM API
	- Interaction
		- `console.log` is very limited: variants for error logging; mostly used for debugging
		- JS designed for document manipulation
		- Inputs from DOM: mouse, text, clicks
		- Outputs to DOM: manipulation of text, colours, etc.
	```js
	const d1 = document.getElementById('d1');
	d1.innerHTML = 'welcome to d1';
	
	const d2 = document.getElementById('d2');
	d2.innerHTML = 'goodbye from d2';
	
	async function demo() {
		console.log('Just starting');
		await new Promise(r=> setTimeout(r,2000));
	
		const d1 = document.getElementById('d1');
		d1.innerHTML = 'welcome to d1';
		
		console.log("After two seconds");
		await new Promise(r=> setTimeout(r,2000));
	
		const d2 = document.getElementById('d2');
		d2.innerHTML = 'goodbye from d2';
		console.log("After four seconds");
	}
	demo();
	
	let x = 0;
	const d1 = document.getElementById('d1');
	d1.innerHTML = `Click count: ${x}`;
	d1.addEventListener('click', e=>{
		x++;
		d1.innerHTML = `Click count: ${x}`
		d1.style.fontSize = `${x+10}px`;
	})
	```

- ## Week 1 GA
	```js
	let startNamePrinter = (name) => {
		let x = name.split('').reverse()
		// console.log(x)
		let handler = setInterval(() => {
			let y = x.pop()
			console.log(y)
		}, 1000)
		/* setInterval is used to create a repeating interval. 
			the interval is set to 1 second
			*/
	
		setTimeout(() => {
			clearInterval(handler)
			}, (name.length +1)*1000)
		/* After a timeout period equal to the length of the original 'name'
			plus 1 second, the 'clearInterval' function is called to stop the interval
			defined by 'setInterval'
			*/
	}
	
	startNamePrinter('orange')
	```

# <u>Week 2</u>
- #### Basic Arrays
	- Collection of objects of any type (can even be mixed type)
	- Element access
	- Length
	- Holes
	- Iteration
- ### Iteration
	- Concepts:
		- Iterable: an object whose contents can be accessed sequentially
		- Iterator: pointer to the next element
	- Iterable objects: arrays, string, map, set, browser DOM (tree structure)
	- Objects: object.keys(), object.entries() – helper functions
	- #### Transformations
		- Functions that take functions as input
		- `map` , `filter` , `find` — apply a callback over each element of array
		- Elements of functional programming: create a transformation chain
		- **Callback**: function passed in to another function, to be called back for some purpose
- #### Other collections
	- Maps: proper dictionaries instead of objects
	- WeakMaps
	- Sets
- ##### Destructuring
	- simple syntax to split an array into multiple variables
	- easier to pass and collect arguments, etc.
	- also possible for objects
- ###### Generator
	- Functions that `yield` values one at a time
	- Computed iterables
	- Dynamically generate iterators
	- Advanced — skip for now
	```js
	// Basic array declaration - mixed mode
	let x = [1,2,3];
	console.log(`${typeof(x)}: ${x} with length = ${x.length}`);
	console.log(x[0]);
	// Mixed element types
	let y = [1,'b', a => a+1];
	console.log(`${typeof(y)}: ${y} with length = ${y.length}`);
	console.log(x.length, y.length)
	// Deleting
	x = [];
	console.log(`${typeof(x)}: ${x} with length = ${x.length}`);
	// Holes
	y.length = 10; // can change the length of an array without inserting elements
	console.log(`${typeof(y)}: ${y} with length = ${y.length}`);
	```

- ### Iterations
	```js  
	// Iteration
	let x = [1,'b',a=> a+1];
	x.length = 5;
	for (let i=0; i<x.length;i++) {
		console.log(`x: ${x[i]} of type ${typeof(x[i])}`); 
	} // will print all 5 elements, including the 2 undefined elements
	for (const i in x) {
		console.log(`x: ${x[i]} of type ${typeof(x[i])}`); 
	} // will ignore the undefined elements and only print 3 elements
	for (const i of x) {
		console.log(`x: ${i} of type ${typeof(i)}`); 
	} // will print all 5 elements, including the 2 undefined elements
	
	let x = {'a':1, 'b':'alpha', 'c':[3,2,1]};
	for (const i in x) {
		console.log(x[i]);
	} // prints all the values because the key index values are iterable
	for (const i of x) {
		console.log(i);
	} // fails because the object x is not iterable
	for (const [k,v] of Object.entries(x)) {
		console.log(v)
	} // Object.entries generates a list of [key,value] pairs
	
	
	// Create arrays with holes
	let x = new Array(5);
	x[1] = 10;
	x[3] = 'hello';
	for (const [k,v] of x.entries()) {
		console.log(`Index ${k}, value: ${v} of type ${typeof(v)}`);
	}
	for (const i in x) {
		console.log(`Index ${i}, value: ${x[i]} of type ${typeof(x[i])}`);
	}
	
	// Spreading 
	let x = [1,2,3];
	let y = [0,...x, 4]; // ... is a spreading operator
	console.log(x); // > [1, 2, 3]
	console.log(y); // > [0, 1, 2, 3, 4]
	
	
	// Iteration and Transformation
	let x = [1,-2,3,-4,5,6,-7,8];
	let y = x.find(t => t<0);
	console.log(x); // > [1, -2, 3, -4, 5, 6, -7, 8]
	console.log(y); // > -2  (returns the first value that it found)
	console.log(x.filter(t => t<0)); // [ -2, -4, -7 ]
	console.log(x.map(t => t>0 ? '+' : '-')); // > [ '+' , '-' , '+' , '-' , '+' , '+' , '-' , '+' ]
	console.log(x.reduce((a,i) => a+i,0)); // > 10   (returns the cumulative output, takes 0 first and add repeatedly)
	console.log(x.reduce((a,i) => a*i,1)); // > -40320
	console.log(x.sort()); // > [-2, -4, -7, 1, 3, 5, 6, 8]
	console.log(x.sort((a,b) => a-b)); // > [-7, -4, -2, 1, 3, 5, 6, 8] (when given a comparison func)
	
	
	// Destructuring
	let x = [1,2,3];
	let [a,b] = x;
	console.log(a); // > 1
	console.log(b); // > 2
	
	// Object destructuring
	const person = {
		firstName: 'Albert',
		lastName: 'Einstein',
		age: 25,
		city: 'Bombay'
	};
	const {firstName: fn, city: c} = person;
	console.log(person);
	console.log(fn); // > Albert
	console.log(c); // > Bombay
	const {lastName, age} = person;
	console.log(lastName); // > Einstein
	console.log(age); // > 25
	
	const {firstName , ...rem} = person;
	console.log(firstName); // > Albert
	console.log(rem); // > {lastName: 'Einstein' , age: 25 , city: 'Bombay'}
	```

- #### Modules
	- Collect related functions, objects, values together
	- "export" values for use by other scripts
	- "import" values from other scripts, packages
	- ##### Ways of implementing
		- script — direct include script inside browser
		- CommonJS — introduced for server side modules
			- synchronous load: server blocks till module loaded (makes the user experience bad)
		- AMD — asynchronous module deifinition
			- browser side modules
		- ES6 Modules
			- both servers and browsers
			- Asynchronous load
	- Node Package Manager: npm
		- Node:
			- command line interface for JS
			- for backend code
	- *look at the 'module' code files in `Week\ 2/` for example code. They need to be run by creating a local server (run this command from terminal `python -m http.server 8000` when in the folder `Week\ 2/` and then go to http://localhost:8000/index.html )*

- ### Class
	- Better syntax — still prototype based inheritance
	- constructor must explicitly call super()
- ### Objects
	- Everything is an object
	- Object literals — used to assign values to names parameters in the object
	- Object methods — used to assign function that can be called on object
	- Special variable `this` (works like `self` in Python)
	- Function methods — call() , apply() , bind()
	- `Object.keys()` , `Object.values()` , `Object.entries()` — use as dictionary
	- ##### Prototype based inheritance
		- Object can have a "prototype"
		- much like 'inheriting' a class in Python
		- Automatically get properties of parent
		- Single inheritance track — always one direct parent relationship, unlike other programming languages
	```js
	let xx = {'a':5 , 'b':'hello'};
	console.log(xx);
	xx.add = function(x,y){ 
		return x+y;
	} // method of xx
	console.log(`xx is of type ${typeof(xx)}`);
	console.log(`xx.add is of type ${typeof(xx.add)}`);
	console.log(`Evaluate the function xx.add(3,4) gives ${xx.add(3,4)}`);
	
	xx.f = function(x) {
		return this.a + x;
	}
	console.log(xx.f(10));
	
	// Copying
	let x = {'a':5 , 'b':2};
	let y = x;
	console.log(x);
	console.log(y);
	x.a = 500;
	console.log(x);
	console.log(y); // y will also change with x because y is just a pointer to x
	
	let z = {...x};
	x.a = 3000;
	console.log(x);
	console.log(y); 
	console.log(z); // z will not change with x because z was made as a copy of x
	
	
	// get and set properties
	let user = {
		first: 'Alberto',
		last: 'Pinto',
		
		get full() {
			return this.first + ' ' + this.last;
		},
		
		set full(f) {
			const parts = f.split(' ');
			this.first = parts[0];
			this.last = parts[1];
		}
	}
	console.log(user.full);
	user.full = 'Gabbar Singh';
	console.log(`Now ${user.first} and ${user.last}`);
	
	
	// Function Methods
	let xx = {'a':5,
			 'b':'hello',
			 'add': function (x,y) {
					 return x+y+this.a;
				 }
			 }
	console.log(xx.add(3,4)); // > 12
	let z = xx.add;
	// call() operator
	console.log(z.call("",3,4)); // z.call takes an additional parameter "" gives the context    Returns NaN
	console.log(z.call(xx,3,4)); // > 12
	// apply() — spreads the arguments — extra ignored
	console.log(z.apply(xx,[1,2,3,4])); // will take 1 + 2 + {xx.a}  and return 8
	// bind() — closure
	let z2 = z.bind(xx,2); // one of the parameters of z is binded to '2'
	console.log(z2(3)); // > 10
	
	
	// Prototypes
	const x = {a:1 , inc: function() {this.a++}};
	console.log(x);
	const y = {__proto__:x , b:2};
	console.log(y);
	console.log(y.a);
	y.inc();
	console.log(x.a);
	console.log(y.a);
	
	
	// Classes
	class Animal {
		constructor(name) {
			this.name = name;
		}
		describe() {
			return `${this.name} makes a sound ${this.sound}`
		}
	}
	let x = new Animal('Jerry');
	console.log(x.describe()); // > Jerry makes a sound undefined
	
	class Dog extends Animal {
		constructor(name) {
			super(name);
			this.sound = 'woof';
		}
	}
	let d = new Dog('Messi');
	console.log(d.describe());
	```

- ### Asynchrony
	- #### Function calls
		- Function is like a 'branch' but must save present state so we can return
		- Call stack
			- Keep track of chain of functions called up to now
			- Pop back up out of stack
	- #### Event Loop and Task Queue
		- Task Queue: Tasks are pushed into queue by events (clicks, input, network, etc.)
		- Event Loop: Wait for call stack to become empty; Pop take out of queue and push it into stack, stack, start executing
		- Run-to-completion: Guarantee from JavaScript runtime; Each task will run to completion before next task is invoked
	- ##### Callback
		- Long running code: will block execution till it finishes
		- Push long running code into a separate "thread" or "task"
			- Let main code proceed
			- Call back when completed

- ### JSON
	- Object notations — for serialisation, communication
	- Notation is frozen — means even problem cases will remain
	- usage through JSON API
	- #### JSON API
		- Global namespace object JSON
		- Main methods: `JSON.stringify()` , `JSON.parse()`
```js
// JSON API
class Animal {
	constructor(name) {
		this.name = name;
	}
	describe() {
		return `${this.name} makes a sound ${this.sound}`
	}
}

class Cat extends Animal {
	constructor(name) {
		super(name);
		this.sound = "Meow";
	}
	static fromJson(o) {
		c = new Cat(o.name);
		c.sound = o.sound;
		return c;
	} // created a new Cat using the object passed into it
}
let c = new Cat('Tom');
console.log(c.describe());

let p = JSON.stringify(c);
console.log(c); // > Cat { name: 'Tom', sound: 'Meow' }
console.log(p); // > {"name":"Tom","sound":"Meow"}

let cc = Cat.fromJson(JSON.parse(p));
console.log(JSON.parse(p)); // > { name: 'Tom', sound: 'Meow' }
console.log(cc.describe()); // > Tom makes a sound Meow
```


# <u>Week 3</u>
- Frontend
	- User Interface (UI) and User Experience (UX)
	- Requirements
		- avoid complex logic — logic to be placed in backend
		- No data storage; risk of data loss
		- Work with stateless nature of HTTP
	- Desirable
		- Aesthetically pleasing
		- Responsive – no lag/latency
		- Adaptive to different types/sizes of screens
	- Programming styles
		- Imperative: sequence of actions to achieve final result ; draw boxes for navigation, main text, fill in text; functions for each step, composition of functions
		- Declarative: specify desired result; compiler / interpreter knows how to achieve result; function integration automated
- #### State
	- Internal details of the system: memory
	- Given a 'system state', the system should always respond the same way to input
	- <u>System state</u>
		- Complete database of amazon.in, flipkart.com : stocks of available items, prices, logged in/registered users
		- All new articles ever published on hindu.com
		- Typically huge, but comprehensive
		- Completely independent of the user interface
	- <u>Application state</u>
		- System as seen by an individual user/session
		- Includes interactivity, session management
		- E.g.: shopping cart, theme, dashboard displays, followed news items
	- <u>UI State</u> (Ephemeral State)
		- part of application actually seen/interacted with
		- Ephemeral — 'lasting for a very short time'
		- E.g.: Loading icons, currently selected tab in multi-tab document
	- Application and UI management
		- HTTP is stateless
		- Client maintains state – sends requests to server for specific items
		- Server maintains state – only specific requests allowed to client

- #### Tic-tac-toe example
	- Using Python-flask
		- everything is handled on the server-side; pretty much nothing on the client-side
		- by maintaining the entire state on the server side, the client has not smart functionality
		- most trivial form
	- Using JS
		- the amount of code written is pretty much the same as in Python-Flask
		- Reloading the page will reset the board, whereas in Python implementation didn't, because Python maintained the state on the server
		- There is no server involved in JS implementation; the state is contained on the page itself
	- Using VueJS
		- changing an element in array: change i-th index of 'myarr'  $\to$ 'new_val': `Vue.set(this.myarr, i, new_val);`
		- declarative programming; no need to call the functions, it'll automatically compute and update the elements.
- Screencast: *refer to the code*

# <u>Week 4</u>
- ### Vue
	- ##### Declarative Rendering
		- Reactivity: Auto-update certain parts in response to changes in data; binding between model (data) and view (display)
		- Focus on **What** instead of **How**
		- Change in one parameter may need multiple updates on screen
		- How?
			- Server tracks *state*: user logged in? date/time?
			- Server responds with complete HTML based on present state: capture different layouts, visibility in views; render appropriately for each user; fully server-side
			- Client-JS: Login controller retrieves user model; client side JS goes through each element and updates as needed
		- Vue – directives
			- `v-bind`: one way binding – update variable, reflects on display
				- `v-model`: two way binding – inputs, checkboxes etc: form data
			- `v-on`: event binding 
	- Class binding
		- Dynamically modify class of an element
		- Special support for bind – object
		- Multiple classes attached based on key-values
	- Conditional rendering
		- `v-if="argument"` : what follows if shown when argument evaluates to true; JS based-changes DOM
		- `v-show="param"` : only if the show parameter evaluates to true; always rendered and present in DOM – only CSS display parameter changed
	- Looping
		- Iterate over any JS iterable: Array, Object, String, etc.
		- usage similar to Jinja {{}} templates
		- `v-for="item in items"` items in an array
		- `v-for="value in obj"` 
		- `v-for="(value,name) in obj"` name -> key: "key" has another meaning in `v-for`
		- `v-for="(value,name,index) in obj"` index -> numerical index
	- Loop keys
		- Looping "creates" new DOM elements: Vue needs to track elements if updating needed
		- For simple updates, simple heuristics are sufficient: for more complex updates, may not be easy to track what has "changed" or what is "new"
		- Provide a "key": key must be unique for each loop element; updating items with same key will automatically update only relevant items
		- Rule of thumb: provide a key where possible – index, ID, ...

- #### ViewModel
	- Model: "data" of the application; usually stored on server in database
	- View: displayed to end user (or to non-human consumer); rendering data
	- View sometimes needs more information than needed for model, or derived information
		- Form with username, password, repeat_password
		- Page with top comments, top posts: should top_comments, top_posts be in the model or be derived from other data
	- Create model constructs with additional data / derived data
	- 'bind' to view (two-way binding)
		- auto update view on change in data
		- (possibly) auto update data when changed in view
	- MVC vs MVVM pattern
		- Vue Model is different from controller but isn't MVVM either
		- Controller conveys action to model and call appropriate view based on inputs and model
		- ViewModel: create framework for data binding and use controllers to invoke actions
	- Computed properties (derived data)
		- derived data updates whenever the source data is changed
		- cached based on their *reactive dependencies* 
		- example: myFontSize is a computer property![[Screenshot 2024-02-15 at 1.32.28 PM.png]]

- #### Watcher
	- explicitly looks for changes and can be used to imperative code
	- For more complex logic than just updating a property
	- anything that could be done with a computed parameter can definitely be done with a watcher
	- Use computed property over watcher whenever possible

- #### Components
	- Reuse
		- e.g. News items on IITM front page, 'people also bought' items on Amazon
		- Same structure, formatting, repeated
		- Refactor: change code without changing functionality; mainly for readability and maintainability – not functionality
	- ##### Vue Component structure
		- Properties: passed down from parent – customise each instance
		- Data: individual data of the present instance
		- Templates: how to render, render functions can be used
			- `{{}}` format – similar to Jinja
			- Safety feature – will not interpolate texts into tags, errors on unclosed divs
			- More complex render functions: JSX mix JS + HTML – similar to React
		- Slot
			- main element of text: use like regular tag
			- properties can be defined in tag
	- example implementation:
		- vue-test1.js:![[Screenshot 2024-02-16 at 7.45.59 PM.png]] index.html: whatever text is written in `<my-card>` tag will go where `<slot>` tag is placed ![[Screenshot 2024-02-16 at 7.46.50 PM.png]]display on the browser: ![[Screenshot 2024-02-16 at 7.48.37 PM.png]]

- #### Reactivity
	- how does reactivity work?
		- Need to track when <u>data is accessed or modified</u>
		- Add methods to objects: everything in JS is an object
	- example: 1st draft![[Screenshot 2024-02-16 at 8.14.54 PM.png]]add new functions: ![[Screenshot 2024-02-16 at 8.15.30 PM.png]]

# <u>Week 5</u>
- Separation of concerns
	- Backend: manage data models
	- Frontend: manage UI
	- Clean interaction mechanism to separate the two
- Requirements
	- System level design with separate backed and frontend
		- Backend doesn't know what UI looks like
		- No direct calls to HTML template rendering, etc.
		- Data output only in neutral formats: JSON preferred
		- Data input through form data or URLs
	- Fetch mechanism
		- How to retrieve data from a backend?
		- URL based APIs
	- Rendering mechanism
		- Frontend can be rendered on server and pushed
		- Frontend implementation in browser, pulls data
- Fetch – Asynchronous
	- Fetching data depends on factors outside server control
		- Latency to backend
		- Network load, disruptions
	- Should not make browser hand if correct data not available
	- Asynchronous operation:
		- start fetch in background
		- wait for results, update

- ### Async
	- #### Callbacks
		- Fucking `doSomething` takes a long time to execute
		- `let result = doSomething()`
			- Entire JS interpreter blocks till result is obtained
			- JS is a single threaded system – browser will hang 
		- Instead start `doSomething` and tell it to call us back when done
	- #### Promise
		- a proxy for a value not necessarily known when the promise is created
		- States of a `Promise`: *pending, fulfilled, rejected*![[Screenshot 2024-02-28 at 5.53.09 PM.png]]
	- Events
		- `button onclick` handler? Essentially becomes a JavaScript function that automatically gets called.
		- Event callback: specify to DOM to invoke a function on particular event
	- ##### JS: Event loops and call stacks
		- Event loops
			- To coordinate events, user interaction, scripts, rendering, networking, and so forth.
			- Multiple window event loops could be cooperatively scheduled in a single thread.
		- Call stack
			- Eecute all operations in present scope in sequence
			- Event loop keeps checking 'callback queue' to see if any new function to be called
			- APIs can put functions in the callback queue ![[Screenshot 2024-02-26 at 5.43.51 PM.png]]
	- #### Callbacks
		- Higher order functions call other functions depending on some conditions
		- Example:
			```JavaScript
			doSomething(successCB, failureCB) {
				let result = doLongComputation();
				if (result) successCB(); // called as function
				else failureCB();
			}
			```
	- Concurrency vs Parallelism
		- Concurrent: multiple operations in process at the same time. T1 and T2 looks as though they're running at the same time but they're actually not ![[Screenshot 2024-02-26 at 7.20.22 PM.png]]
		- Parallel: multiple concurrent operations physically executing at the same time. Actually have 2 CPUs. T1 runs on CPU1 and T2 runs on CPU2
	- #### Async op: fetch
		- Fetching a URL must be async
		- JS API since ES6: `fetch()`
			- Implemented using `Promise`
			- Built into most browsers
	- ###### Axios
		- custom API library similar to fetch
		- also works on nodejs

- ### Existing APIs
	- Building a frontend
		- Significant development possible with just API access

- ### Screencast
	- #### VueJS Lifecycle ![[Screenshot 2024-02-27 at 10.21.38 PM.png]]![[Screenshot 2024-02-27 at 10.22.33 PM.png]]![[Screenshot 2024-02-27 at 10.22.57 PM.png]]![[Screenshot 2024-02-27 at 10.23.30 PM.png]]
	- #### Async and wait
		- Async functions
			```javascript
			async function say_hello() {
				return "hello";
			}
			console.log("before");
			wish= say_hello();
			console.log(wish); // returns a Promise
			/* Promise is way of browser telling you that I'm going to return the actual value
			sometime later
			*/
			wish.then((v) => console.log(v)); // this will resolve the Promise; will wait till Promise changes state to fulfilled
			console.log("after");
			```
		- Typical example of an async function
			```javascript
			async function say_hello() {
				return new Promise((resolve, reject) => {
					// resolve after two seconds
					// you could be doing non CPU stuff
					setTimeout(function() {
						resolve("async hello");
					}, 2000); // delay of 2 seconds and then resolving "async hello"
				});
			}
			console.log("before function call");
			wish= say_hello();
			console.log(wish); // returns a Promise
			/* Promise is way of browser telling you that I'm going to return the actual value
			sometime later
			*/
			wish.then((v) => console.log(v)); // this will resolve the Promise; will wait till Promise changes state to fulfilled
			console.log("at the end");
			```
		- catching an error with async Promise function
			```javascript
			async function say_hello() {
				return new Promise((resolve, reject) => {
					// resolve after two seconds
					// you could be doing non CPU stuff
					setTimeout(function() {
						reject("error: async hello");
					}, 2000); // delay of 2 seconds and then resolving "async hello"
				});
			}
			
			say_hello()
			.then((v) => console.log(v)) // goes here if succeeds
			.catch( e => {               // goes here if there's an error
				console.log("GOT ERROR")
				console.log(e);
			})
			```
		- `Await` functionality
			```javascript
			async function say_hello() {
				return new Promise((resolve, reject) => {
					// resolve after two seconds
					// you could be doing non CPU stuff
					setTimeout(function() {
						resolve("async hello");
					}, 2000); // delay of 2 seconds and then resolving "async hello"
					// reject("Promise rejected"); // will throw rejection error
				});
			}
			async function greetings() { 
				console.log("before");
				wish= await say_hello();
				console.log(wish);
				console.log("after");
				return wish
			}
			
			greetings();
			```
			- `await` is only valid in async functions, generators and modules
		- catching error using `await`
			```javascript
			async function say_hello() {
				return new Promise((resolve, reject) => {
					// resolve after two seconds
					// you could be doing non CPU stuff
					setTimeout(function() {
						reject("error: async hello");
					}, 2000); // delay of 2 seconds and then resolving "async hello"
					// reject("Promise rejected"); // will throw rejection error
				});
			}
			async function greetings() { 
				console.log("before");
				try {
					wish= await say_hello();
					console.log(wish);
					console.log("after");
					return wish
				} catch (e) {
					console.log("GOT ERROR!");
					console.log(e);
				}
				return null
			}
			
			greetings();
			```
	- #### Fetch API
		- `fetch()` starts the process of fetching a resource from the network, returning a promise which is fulfilled once the response is available.
		- The promise resolves to the `Resources` object representing the response to your request.
		- This promise will reject only if there is a network error, but not when there is an HTTP error (page not found, etc.). So we will have to do response status check.
		- For more info, go [here](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
		```javascript
		fetch("https://httpbin.org/uuid")
			.then(response => response.json()) // first promise
			.then(data => console.log(data)); // handling the response.json promise
		
		// Handling HTTP error
		fetch("https://httpbin.org/uuid/404")
			.then(function(response) {
				console.log(response)
				if (!response.ok) {
					console.log("Response not okay");
					// we throw an error
					throw new Error('HTTP error, status = ' + response.status);
				}
				return response.json();
			})
			.then(function(data) {
				console.log('Got data', data);
			})
			.catch(function(error) {
				// we can catch and do something
				console.log("IN catch", error);
			});
		
		// Send JSON data using fetch
		data = {'name':'Akul' , 'city':'Mumbai'};
		fetch('https://httpbin.org/post', {
			method: 'POST',
			headers: {
				'Content-Type' : 'application/json',
			},
			body: JSON.stringify(data),
		})
			.then(response => response.json())
			.then(data => {
				console.log('Success:', data);
			})
			.catch((error) => {
				console.error('Error: ',error);
			});
		
		// form submission using fetch
		form = new FormData(document.getElementById('my-form')); // reference to form by form-id
		fetch('https://httpbin.org/post', {
			method: 'POST',
			body: form
		});
		
		// Download a file using fetch
		fetch('https://httpbin.org/image/jpeg').then((response) => {
			console.log("Got it")
			return response.blob();
		}).then((myBlob) => {
			console.log(myBlob)
		}).catch((error) => {
			console.log('Error: ' + error.message);
		});
		
		// Standardising fetch requests
		myHeaders = new Headers();
		myHeaders = {'Content-Type': 'application/json'};
		const myRequest = new Request('http://httpbin.org/post', {
			method: 'post',
			headers: myHeaders,
			mode: 'cors',
			cache: 'default',
		});
		fetch(myRequest)
			.then(response => response.json())
			.then(data => console.log(data));
		
		// Using await instead of resolving the promises manually
		response = await fetch("https://httpbin.org/uuid");
		data = await response.json();
		console.log(data);
		```
	- #### VueJS – API calls
		- *check changes in 'methods' of the Vue component. File: Week 5/vuejs_APIcalls/application.js*

# <u>Week 6</u>

- #### Persistent Storage
	- True persistence possible at server
	- ###### How?
		- <u>Cookies</u>: JS setCookie() can be used for simple data; limited storage – usually session temporary
		- <u>localStorage</u>: built-in API in browser to save simple key-value entries; complex objects should stringified – use JSON
		- <u>IndexedDB</u>: Transactional database system; Object-oriented JS-based DB; store and retrieve objects with key
	- ##### localStorage
		- a part of WebStorage API; [more info](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)
		- sessionStorage: storage ends with session (browser restart) ; more storage than cookies (~ 5MB)
		- localStorage: persists across browser restarts; browsers may implement limits to avoid overload 
		- [more info](https://v2.vuejs.org/v2/cookbook/client-side-storage)
		- example code:
			```html
			<!-- html file: -->
			<div id="app">
				My name is <input v-model='name'>
			</div>
			```
			```javascript
			// js for the above html file:
			const app = new Vue({
				el: '#app',
				data: {
					name: ''
				},
				mounted() { 
					if (localStorage.name) {
						this.name = localStorage.name;
					} // load the variable in the form after mounted
				},
				watch: { 
					name(newName) {
						localStorage.name = newName;
					} // update the value of localStorage variable anytime there's a change in 'name'
				}
			});
			```

- #### Form Validation
	- Validation: check whether data entered meets certain criteria; 
		- Text field contains numbers, email address, etc.
		- Select field has at least one entry
		- Server side checks: essential in many cases for security; more costly, increases server load
	- Vue and validation
		- Data binding and reactivity
			- Easy updates of parts of DOM
			- Selectively display error messages: `v-if`, `v-show`
		- `v-model` connects fields with JS variables for easy processing
		- `preventDefault()` – stop normal processing of form unless check successful
			- for example if you want to override some of the checks that are in the browser. You click on the submit button, JS takes over, performs all the checks. If it finds something is wrong, it blocks the operation.
			- connect as `submit` event handler
	- Custom validation
		- e.g.: custom email check: specific domain, specific number of characters, etc.
		- e.g.: check for certain overall condition
		- Need to prevent regular form validation: `novalidation=true` in form definition
		- [more info](https://v2.vuejs.org/v2/cookbook/form-validation)
		- example code:
			```html
			<!-- html file: -->
			<form
				  id="app"
				  @submit="checkForm"
				  action="https://vuejs.org/"
				  method="post"
			
				<p v-if="errors.length">
					<b>Please correct the following error(s):</b>
					<ul>
					<li v-for="error in errors">{{ error }}</li>
					</ul>
				</p>
				
				<p>
					<label for="name">Name</label>
					<input 
						id="name"
						v-model="name"
						type="text"
						name="name">
					
				</p>
			
				<p>
					<label for="age">Age</label>
					<input 
						id="age"
						v-model="age"
						type="number"
						name="age"
						min="0">
					
				</p>
			
				<p>
					<label for="movie">Favorite Movie</label>
					<select 
						id="movie"
						v-model="movie"
						type="movie"
						name="name">
					
					<option>Star Wars</option>
					<option>Vanilla Sky</option>
					<option>Atomic Blonde</option>
					</select>
				</p>
				
				<p>
					<input type="submit" value="Submit">
				</p>
			</form>
			```
			```javascript
			const app = new Vue({
				el: '#app',
				data: {
					errors: [],
					name: null,
					age: null,
					movie: null
				},
				methods: {
					checkForm: function (e) {
						if (this.name && this.age) {
							return true;
						}
						
						this.errors = [];
						
						if (!this.name) {
							this.errors.push('Name required.');
						}
						
						if (!this.age) {
							this.errors.push('Age required.');
						}
						
						e.preventDefault();
					}
				}
			})
			```

- #### Managing Components
	- When creating components, their names go to Global namespace, so each component needs to have a unique name.
	- String templates in components are harder to edit and manage with regular editors
	- CSS: No block scoping – only global CSS ; Nor modular unlike HTML and JS
	- No build step – backwards compatibility not easy, cannot use tools like Babel
	- SFC — Single File Component![[Screenshot 2024-03-01 at 5.03.13 PM.png]]
	- Separation of concerns
		- SCF does not require separate files
		- Semantic content – HTML
		- Presentation – CSS
		- Logic – JS
	- Extra "Tooling"
		- JS cannot directly read .vue files
		- Compilation needed: convert .vue to .js + .css + .html
		- npm: Node Package Manager
			- Systematically managed JS modules
			- Import new modules as needed
		- Mostly managed from Command Line Interface

- #### Testing
	1. Unit Testing
		- As with any software process
		- Components are good units to test
		- Can "mount" into a testing DOM
	2. E2E (End-to-End) testing
		- Full application including backend (much like Flask app)
	3. Cross-browser testing
		- Compatibility with older browsers
	- Mechanisms
		- Set up fixtures: prepared data
		- Test Suite: collect several tests together ; test one component
		- Tools: mocha, chai, jest : supporting functions to test for presence/absence of elements
		- [more info](https://v2.vuejs.org/v2/cookbook/unit-testing-vue-components)

- #### Vue Routing
	- Vue routing when building a single page app
	- Single Page Applications – web applications that mimic desktop application; refreshing data in the background; no need to download templates; no delay; no refresh of the screen
	- [To get started](https://router.vuejs.org/guide/)
	- *refer to the codes*

# <u>Week 7</u>
- #### State Management
	- UI = f(State) ; UI is a function of the state. Given a state, the UI should be programmatically derived from there, shouldn't depend on other factors
	- State management pattern:
		1. <u>State</u>: "Source of truth" about internals of the app
		2. <u>View</u>: function of State – declarative mapping
		3. <u>Actions</u>: view provides input (actions); state changes in response to action
		- One-way data flow
	- here we're only concerned with UI state, as opposed to the MVC model which also looked at the system state. MVC can still be used on server to update system state
	- Hierarchy – multiple components
		- Parent -> child : pass information through props (properties)
		- Chile -> parent : pass information through events; can directly invoke parent functions or modify parent data (not desirable because harder to debug)
	- Problem with multiple components
		- Multiple views may depend on same piece of state
		- Actions from different views may try to modify state
		- "Sibling" components
			- At same or similar levels of hierarchy
			- Pass events up from source until common parent
			- Pass props back down to destination
		- Solution:
			- Don't use global variables
				- Keeping track of who modified a global variable is difficult
			- Use <u>Restricted Global</u> variables
				- Global required so all components can update their views easily
				- Changes to the variable constrained
					- no direct modification of state variable
					- only through special mutation actions
	- <u>Flux</u>
		- primarily meant for React
		- Unidirectional data flow
			- store – maintains the state variables
			- dispatcher – sends action messages
			- view – React components that update based on state
	- <u>Redux</u>
		- Single source of truth
		- State is read-only: explicitly return a new state object: easier to trace
		- Changes made by "pure" functions – no side effects: changes easy to trace
	- <u>Elm architecture</u>
		- Elm: functional language designed for web application development
		- Model – state of your application
		- View – way to turn your state into HTML
		- Update – way to update your state based on messages ![[Screenshot 2024-03-13 at 1.16.15 PM.png]]
- #### Vuex
	- state management library for Vue
	- introduces a new "store" that is globally accessible
	- officially supported by Vue
	- Example:
		- Vuex Store
			```js
			const store = new Vuex.Store({
				state: {
					count: 1
				},
				mutations: {
					increment (state) {
						// mutate state
						state.count++
					}
				}
			})
			```
		- Use in Component
			```js
			const Counter = {
				template: `<div>{{ count }}</div>`,
				computed: {
					count () {
						return store.state.count
					}
				}
			}
			```
	- Single shared state object
		- Tree structure to capture component nesting
		- Similar constraints on data to Vue data object
	- Components can still have local state
		- Not to be seen/used outside component
	- Getter methods: 
		- computed properties on shared state objects
	- Access within components
		- `this.$store` available within all components
	- ##### Mutations
		- to change state: "commit" a mutation
		- Never directly update a variable
			- Always call a method that updates
			- Explicitly "commit" this action – ensure it can be tracked and recorded
		- Must be **synchronous**
		- Example:
			```js
			//...
			mutations: {
				increment (state,n) {
					state.count += n
				}
			}
			```
		- Usage scenario:
			- Normal: `store.commit('increment')`
			- With argument: `store.commit('increment', 10)`
			- Object
				```js
				store.commit({
					type: 'increment'
					amount: 10
				})
				```
	- Debugging
		- Recorded in devtools
			- Allows "time travel" debugging – retrace steps that caused a problem
		- List of all mutations requested, who requested, time of request
			- can play back mutations in order from beginning
			- reproduce system state at any point – time travel...
	- ##### Actions
		- Mutations must be synchronous – no async calls permitted
			- some data updates may not be possible to sync
		- Actions can contain async functionality
			- do not change state directly: commit mutations
		- Example:
			```js
			//..
			actions: {
				increment ({ commit }) {
					commit('increment')
				}
			}
			```
			- Then to call: `store.dispatch('increment')`
		- composing actions ![[Screenshot 2024-03-13 at 4.55.33 PM.png]]

- #### Routing
	- Page composition
		- Original: all pages are HTML from server
		- Vue-like frameworks:
			- components
			- parts of app can correspond to components instead of HTML pages
			- application – not just sequence of pages
	- Example:![[Screenshot 2024-03-13 at 5.12.01 PM.png]]whatever component is  matched by the present route will be rendered in the `<router-view></router-view>`; need the notion of what is the 'current route'.![[Screenshot 2024-03-13 at 6.46.55 PM.png]]
	- *Also, refer to Week 6 screencast codes*
	- Advantages
		- clickable links to transition between components
		- clicks handled by client JS, no need to hit server
		- can replace parts of existing page – limit refreshes
	- #### Dynamic routes![[Screenshot 2024-03-13 at 6.51.51 PM.png]]
		- Impact on reactivity:
			- when navigating from `/user/one` to `/user/two` reuses same component, it may not trigger reactive updates
			- <u>solution</u>: install a watches on `$route` object![[Screenshot 2024-03-13 at 6.54.20 PM.png]]

- #### Single Page Application
	- Asynchronous fetch only required data to update parts of page
	- Page transitions and history handled through JS
	- Dynamic website; rewrite current page instead of re-rendering with fresh load
	- <u>How?</u>
		- Transfer all HTML in one request
			- Use CSS selectors, display controls to selectively display
			- Large load time, memory
		- Browser plugins
			- Java applets, Shockwave Flash, Silverlight
			- Significant overhead, compatibility issues
		- AJAX, fetch APIs
			- Asynchronous fetch and update parts of DOM
			- Most popular with existing browsers
			- Requires powerful rendering engines
		- Async transfer models
			- Web-sockets, server-sent events
			- more interactive, can be harder to implement
	- Impact on server
		- Thin server
			- more load on the client-side
			- only stateless API responses
			- All state and updates with JS on browser
		- Thick stateful server
			- server maintains complete state
			- requests from client result in full async load, but only partial page refresh
		- Thick stateless server
			- client sends detailed information to server
			- server reconstructs state, generates response: only partial page refresh
			- scales more easily: multiple servers need not sync state
	- Running locally
		- Can be executed from a `file://` URI
		- Download from server, save to local filesystem; subsequent requests served locally
		- Use WebStorage APIs
	- Challenges
		- Search engine optimisation; links are often local, or #
		- Managing browser history; can confuse users, browser history API changes
		- Analytics; tracking popular pages not possible on local load
	- #### SPA with Vue
		- Complex application logic: Backend on server (Flask, etc.)
		- Frontend state variables: Vue + Vuex
		- Navigation and page updates: Vue router; component based
	- #### Progressive Web Apps
		- Not all SPAs need to be PWAs: may be a single page but without web workers, offline operation, etc.
		- Not all PWAs need to be SPAs: may have offline and web workers, where rendering is done on server/web worker, not JS
		- ##### Web Workers
			- Script started by web content (runs in the background)
			- worker thread can perform computations, fetch requests
			- send messages (events) back to origin webcontent ![[Screenshot 2024-03-13 at 7.30.03 PM.png]]
		- Characteristics
			- Instal-lability
			- Web Manifest: metadata to identify to operating system
			- WebAssembly (compiled version of JS): faster operation possible
			- Storage: Web storage APIs
			- Service workers
			- [PWA example website](https://app.diagrams.net/)

- ##### Web apps vs Native
	- Native:
		- compiled with SDKs like Flutter, Swift SDK
		- Best access to underlying OS
		- Restrictions minimised with OS support
		- Look and feel of native, but not uniform across devices
	- Web apps:
		- write once, run anywhere (original Java slogan)
		- simple technologies, low barrier to entry
		- evolving standards

# <u>Week 8</u>
- #### Designing APIs
	- Purpose of an API: To be **used** to build applications
	- Data oriented approach
	- Possibilities (of endpoints)
		- List of students: \http://localhost/getListOfStudents
		- Individual student: /getStudent?id=xyz
		- Add new student: /createNewStudent
		- Edit existing student: /editStudent?id=xyz
	- Use **Conventions**
		- List of students: \http://localhost/students
		- Individual student: \http://localhost/student/123
		- Add new student: POST .../student
		- Edit existing student: PATCH .../student/123
	- Nouns in URL are good, verbs are bad
	- Permalinks: not human readable; unique ID for posts, documents, etc.
	- Query URLs
		- '/search?course=123&type=student' OR '/course/123/students'
		- Convention: structured URLs preferred by developers
		- Why not '/course-123-students'? has to be parsed – more work at the server end
	- HTTP Verbs
		- <u>GET</u>: read data, lists, etc.; cacheable – all data is i URL
		- <u>POST</u>: create new object/data; not cacheable in general; can be used for reading data
		- <u>PUT/PATCH</u>: update with all new data; PATCH preferred for incremental data
	- Output formats
		- Structured data
			- XML: very good
			- JSON: not so good – very limited data types
		- Simplicity: JSON – human readable; easy to parse
		- JSON + extensions is preferred format
	- Include self-link (the endpoint that sent the JSON) and additional links that give pointers to other useful information![[Screenshot 2024-03-14 at 1.36.29 PM.png]]
	- Authentication
		- Token based authentication
		- OAuth2: good standard used in many places
		- JWT (JSON Web Token) and other variants possible
	- Problems with REST
		- Most "RESTful" APIs are violating some constraint of REST
		- REST is an architecture style, not an API design document
		- Multiple requests to fetch data for a view
		- Specific requests permitted – not a general "Query language"
		- cannot specify 'what is needed' – need to break up into individual stages of how to get the result
- ##### GraphQL
	- Helps with more complex querying than REST based API
	- Declarative programming
	- Engine on the server side to handle requests
	- Translate requests in a complex query language to data requests
	- Query language
	- can be used over HTTP
	- send complex queries over POST body
	- layer between client and server
	- allows you to specify data type
	- API versioning: requests are JSON-like; add functionality as required without needing to declare new API version
	- connect to multiple backends; define own resolvers
- #### Markup Alternatives
	- Text-based markup
		- almost like normal text
		- Markdown, ReStructured Text, AsciiDoc
	- Why text
		- uniform character representation agreed upon
		- guard against obsolescence
		- compact
		- easy for humans to read
	- Why *not* text
		- hard to encode
		- ambiguity possible
		- more focused towards english and roman alphabets
	- Compile/convert
		- systematic conversion between markup formats
		- easier between structures languages
	- Mixed functionality
		- programs mixed with documentation: Web/Weave, Doxygen and similar comment-oriented sytems
		- JSX, Vue
			- mix JS with templates and HTML structure
- #### JAM (JavaScript APIs Markup)
	- What does an app need?
		- Data storage: APIs for access and retrieval; SQL, NoSQL, etc.
		- User interface: Vanilla HTML+forms; JavaScript for more interactivity
		- Business Logic: Backend computation (Python, Go, NodeJS); Frontend computation (JS, WASM)
	- Content Management Systems (example for a blog application)
		- CRUD and ratings for posts, comments;  user management; analytics
		- All are data manipulation, independent of user interface
	- Wordpress
		- handles both data storage and templating
		- Also provides API
		- API can be used to build a CMS without frontend
	- Static Site Generators
		- NextJS, NuxtJS, Gatsby, etc; JS based, useful for interactive sites, complex designs, plugins
		- Jekyll, Hugo; primarily text oriented; blogs, home pages
	- JS hydration
		- Static HTML transferred from server – no interactivity
		- 'Hydrate' the HTML with event handlers: inject interactivity after initial rendering complete
		- Delayed, but still fast enough: good combination of speed and interactivity

- ### Screencast
	- Flask API – Token based authentication ([link](https://www.youtube.com/watch?v=4NSW7IM8Sr4&ab_channel=IITMadras-B.S.DegreeProgramme))
	- Integrating Vue with Flask ![[Screenshot 2024-03-19 at 7.04.30 PM.png]]

# <u>Week 9</u>
- #### Web server
	- Simplest possible HTTP server: Open port 80 in "listen" mode – wait for incoming connections; listens for incoming connects; send back a response
	- Flask in "non-threaded" mode blocks the server until the current request is completed before accepting the next request
	- Threaded web server
		- Accept incoming request
		- Immediately start a thread to handle request
		- Go back and listen for next request
		- Limitations:
			- each thread consumes resources
			- depends on OS for handling parallel / concurrent execution
- ##### Asynchronous Task Frameworks
	- Goals:
		- User can define set of tasks
		- Web server can "dispatch" tasks to be executed later
		- Asynchronous completion and updating possible
	- When to use?
		- Response to user does not depend on execution of task
			- Example: send email – can display a "sending" message and later update status
		- Example of when **NOT** to use:
			- API fetch: response must be based on result of API query
			- async task will not help since you will need to block and wait for response
		- Note: this is NOT the same as async on frontend
			- Async frontend with UI reactive update is still useful
			- But the backend process should return with the correct response
- #### Message Queues
	- when there are multiple servers that need to communicate with each other to handle the coordination of task execution, there needs to be "messaging" among them
	- Communication between servers
		- Many-to-many: point to point connections (but doesn't scale well)
		- Scaling: add new servers
		- Assymetric
			- not all servers need to talk to each other
			- some produce messages, some consume
		- Failure to tolerance
			- offline servers – failover
			- busy servers – retry
	- Messaging
		- <u>Decouple</u> message from execution: server for execution sends a message – another server picks it up
		- <u>Asynchronous</u> communication – no need to wait for response – or response or may be delayed
		- <u>Dataflow</u> processing – react to presence of messages; automatically adjust to rate of processing determined by activity
		- <u>Ordered</u> transactions – first-in-first-out
	- Message broker![[Screenshot 2024-03-25 at 5.59.32 PM.png]]
	- ##### Benefits of message broker
		- Scalability: can easily add servers
		- Traffic spikes: messages retained in queue until processed – may be delayed, but not lost
		- Monitoring: easy point of reference for monitoring performance: number of messages unprocessed
		- Batch processing: collect messages into a queue and process them at one shot
	- Variants:
		- Message Queues
		- Pub/Sub: Fanout
		- Message Bus
		- APIs / Web services
		- Databases
	- Advanced Message Queueing Protocol – AMQP
		- Standard similar to HTTP, SMTP: details of how to connect, initiate transfers, establish logical connections, etc
		- Many open-source implementations: RabbitMQ, Apache ActiveMQ, etc.
		- Broker
			- Manage transfer of messages between entities
			- "Message exchange" intermediary – clients always talk to exchange
		- RabbitMQ: well suited for complex message routing
	- Redis
		- In-memory database
			- key-value store
			- Not originally designed for messaging at all
		- Pub/Sub pattern
		- Very high performance due to in-memory but lacks persistence – data lost on shutdown
		- Excellent for small messages: performance degrades for large messages

- #### Asynchronous Tasks with Celery
	- Task Queues
		- User request handler "pushes" task onto a queue: FIFO
		- Separate queue mangers to handle execution of tasks and returning results
	- Asynchronous Task Execution
		- Language supported: Python asyncio ; JS async/await
		- Guarantees of completion
		- Reliable against server failure
		- Ability to auto-retry
	- Pushing a task onto a queue should be faster than executing the task
	- There should be enough worker resources to empty the queue eventually
	- Potential problems
		- Deadlock and related issues
		- Buffer sizing, overflows
	- <u>Push Queue</u>
		- Client pushes task onto server queue
		- Server *should* start operations "immediately" (may be delayed based on availability of resources)
		- Closer to "real-time" operation
		- Examples:
			- update friend list in social media application: push updates to DB for all friends
			- Send emails: push emails onto queue to be sent out individually
	- <u>Pull Queue</u>
		- Clients can push tasks at any time
		- Server "polls" queue at regular intervals
		- Better suited to "batch-mode" operation: Generally not real-time
		- Examples:
			- Batch update of high scores in gaming server: periodic updates
			- Dashboard updates – process many log entries in batch and update periodically
		- Pull mechanisms
			- Polling: Periodically check on state of queue; CPU / network intensive due to repetitive function calls
			- Long poll
				- Server keeps connection open until data present
				- Client blocks until data received
	- Task Queue high end example:
		- Google AppEngine
		- Tencent cloud
		- AWS
			- SQS – simple queue service – messaging
			- worker tasks implemented separately
	- General use task queues
		- Celery – python library
		- RQ – Redis Queue
		- Huey, Django-carrot, ...
	- #### Celery
		- Python package for handling asynchronous tasks
		- Requires a separate broker for messaging
		- Also a backend for collection and storing results
		- Multiple celery instances can "auto-discover" through the messaging system
		- Abstracts away the messaging system to focus on tasks
		- <u>Using Celery</u>
			- Problem: multiple moving parts
				- message broker
				- result collector
				- celery instance to run workers
				- actual code
			- Installing and managing needs care
			- Use when needed
			- Can use on platforms like replit (requires a little extra work)

- ### Screencast
	- #### Redis ([link](https://www.youtube.com/watch?v=ygUDWhb0ZmQ&ab_channel=IITMadras-B.S.DegreeProgramme))
		- In-memory storage. Stores data in cache. 
		- Doesn't work like a regular RDBMS. If you were to use Redis as data storage, treat it like NoSQL
		- Every key-value pair can be given a "TTL" value (Time To Leave). Once the TTL value reaches 0, it deletes that particular key-value pair
		- <u>Pub/Sub</u>
			- very useful for messaging platform
			- useful for running job queues, alert messages, etc.
		- Supports transactions, like a regular NoSQL database
	- #### Celery ([link](https://www.youtube.com/watch?v=oK_lUKTzDiI&t=2548s&ab_channel=IITMadras-B.S.DegreeProgramme))
		- package in python that allows us to run jobs and workers separate from the web server.
		- Users sends a request via Flask, which gets queued in the "Message Broker". Each request is taken by the worker(s) one at a time. Once the task is complete, the result is inserted in the "Result Backend", which is then accessed by the Flask App. This entire cycle works asynchronously.![[Screenshot 2024-03-26 at 12.07.42 PM.png]]

# <u>Week 10</u>
- #### Inter-Service Messaging
	- Message Queues
		- Multiple services: closely coupled; running on same or closely related servers
		- example: frontend, email, database, image processing
		- Asynchronous message delivery
			- speed of front-end is only restricted by the speed of sending messages
		- Guarantees of delivery
	- ##### Internet-distributed Services
		- No common message broker
		- Servers expose services for public use
		- May not need delivery or order guarantees
		- Lightweight messaging![[Screenshot 2024-03-31 at 7.53.48 PM.png]]
	- Lightweight API calls
		- Server expose certain endpoints
		- Meant for other to PUSH messages, not retrieve data
		- Requests usually done through POST, maybe GET
		- Data payload may be trivial or even non-existent
	- Examples
		- Every time there is a commit pushed on github, send a message on Google chat room
			- github allows you to register a URL
			- you create a server to receive the request and then push to GChat
			- Github provides you with some mechanism whereby you can call your own function that can then send the message to GChat
		- Use Twilio to send several messages
			- Twilio calls you back when done with messages
			- You don't have to keep checking status from Twilio

- ### Webhooks
	- they use existing web infrastructure to send messages
	- primarily for server to server communication
		- can also be direct client invoking hook on server
	- simpler than message queues
	- A way for an "app" to provide other "apps" with real-time information
	- a.k.a <u>web callback</u> or <u>HTTP Push API</u>
	- Sometimes called reverse API
		- similar specification to regular APIs
		- usually only to push information, not retrieve data
	- Synchronous
		- No store, retry, etc. — may trigger other behaviour, but webhooks response must be immediate
	- Example webhook: gitlab
		- Setting up a receiver
			- [Request bin](https://pipedream.com/requestbin)
				- Any request made to the URL gets logged
			- Gitlab
				- Register for "webhooks" in the settings of a repository. Use the URL from Request bin.
				- Can "Test" webhooks in Gitlab itself
		- *prof creates his own webhook using Flask on replit and adds it to GitLab*
	- Message content
		- application dependent
		- keep to minimum: not meant to transfer large amounts of data; only as a message
	- Message response
		- Webhooks are "machine called": invoked by another server, not a human client
		- Response should just indicate status (e.g.: the Flask app implemented by prof only sent back 200 HTTP status code)
			- Minimal data returned – mostly will be discarded
	- Different ways of doing communications![[Screenshot 2024-04-02 at 2.50.21 PM.png]]
	- How to?
		- Consume webhook: Create URL endpoint, register with provider (eg. gitlab, twilio,...)
		- Debugging
			- requestbin: dummy endpoint to receive data and see content
			- API debugging tools: curl or postman
			- ngrok: public URL endpoint for private code without needing public IP
		- Securing webhook:
			- Restrict at IP access level is difficult for public facing
			- Use API key/access token/header: eg. X-Gitlab-Token header

- #### Push to Client
	- Client-side updates
		- Requires persistent connection to/from client
		- Pull vs Push
			- Client can pull updates
			- Server can push updates
		- Original HTTP spec provided no support for this
			- Connection is stateless
			- Client-side pull easy – always possible with page refresh
	- ##### Polling
		- Client repeatedly sends requests
		- Fixed Interval polling
			- easy to implement at client
			- Server may not have any updates – unnecessary work
			- Can overwhelm server if too many clients
		- Variable interval: long poll
			- Server blocks until it has something to update
			- Keep connection open – data sent only when needed
			- Occupies server resources
		- [Long polling example in javascript](https://javascript.info/long-polling)
	- ##### Server-sent Events
		- Mechanism for server to "push" events
		- Requires WebWorker (service worker) on client
		- Service worker can continue running in background
		- Receive update, push to page
	- ##### Push notifications 
		- JS Push API
		- Web Push Protocol
		- Message urgency, priority possible
		- Service worked on client receives and updates
	- ##### Public push notification providers
		- Alternatives
			- Firebase Cloud Messaging (previously Google Cloud Messaging)
			- Apple Push
		- Authenticated and registered with app
		- Web apps vs native apps
			- Web tech (HTTP) vs custom connections (TCP)

- ### Screencast
	- #### Server Sent Events
		- [link](https://www.youtube.com/watch?v=s9ShXWD1kK8&ab_channel=IITMadras-B.S.DegreeProgramme)
	- #### How to Use Webhooks
		- [link](https://www.youtube.com/watch?v=LM-I_aCt3ac&ab_channel=IITMadras-B.S.DegreeProgramme)

# <u>Week 11</u>
- ### Performance
	- Speed: single-user performance; user experience; network
		- Contributing factors: network; number of requests; size of response; HTTP 1 vs 2; compression
		- Tools:
			- controlled and measured access to all elements of site
			- Lighthouse – popular tool built in to Google Chrome
	- Scaling: multi-user performance; server load; cost
	- #### Lighthouse
		- loads a page and all resources while monitoring time taken
		- measure time, memory metrics
		- emulate network bottlenecks, throttling, etc.
		- emulate devices: mobile vs desktop
		- compute weighted average score based on performance, accessibility, SEO, PWA, and best practices
		- ##### Performance metrics
			- First Contentful Paint: how long does it take (after typing in a link) to display something related to that link, on the screen
			- Speed Index: capture video of page loading and analyse
			- Largest Contentful Paint: "Most of page" rendered
			- Time to Interactive: Usability of page
			- Total Blocking Time: Time blocked from responding to user; mostly JS related
			- Cumulative Layout Shift: rearrangement of page after some more data loaded

- ### Scaling
	- Static vs. Dynamic
		- Static: predominantly user-neutral content; example: blogs
		- Dynamic: user customisation; example: e-commerce
	- Response under load: requests per second; example: google search, bing
	- Response under sudden **changes** in load: rate of change; example: declare IPL scores
	- Predictable or not?
		- prepare in advance for the increase in load
	- Components of App
		- Server
			- frontend
			- database
			- load balancer
			- proxy – handles some queries without loading server
		- Network
			- mobile – speed, signal quality, movement, congestion
			- broadband – shared connection, wire quality
		- Application
			- data intensive
			- image/script intensive
			- browser/client functionality
	- <u>Server: Load Balancing</u>
		- Load balancer:
			- minimum functionality – purely forward requests
			- Round-robin, least load, etc.
		- Commercial offerings
			- Amazon Elastic Load Balancing, Google Cloud Load Balancing
			- Distribute load across VM machines, IP addresses, etc.
	- <u>Server: Proxy</u>
		- Intermediate layer between client and server
		- Caching proxy can inserted at various stages; close to client for faster responses
		- Content Delivery Networks (CDN)
			- form of proxy, but explicitly encoded in URL
	- <u>Server: DB</u>
		- choice of DB
			- SQLite, PostgreSQL, MySQL, Oracle
			- MongoDB, Cassandra, Amazon Dynamo
		- Scaling
			- SQLite difficult to scale for writing, great for reading
			- Synchronisation, Replication issues
	- <u>Server: Language</u>
		- Interpreted languages easy to develop: Python, JS
		- Compiled languages harder, but much faster: C, Golang, Java
		- Threading and Asynchronous capabilities: Goroutines, JS Async, Erlang/Elixir
		- Programming paradigms
			- Functional
			- Declarative
			- Imperative
	- Tools for live monitoring:
		- ElasticSearch / LogStash / Kibana
		- Grafana + InfluxDB + Prometheus

- ### Caching
	- What?
		- store response to requests so they can be reused for future reqeusts
		- largely developer controlled
		- where: server, proxy frontend, network router, client
	- ![[Screenshot 2024-04-12 at 7.28.24 PM.png]]
	- Server supporting for caching
		- HTTP Headers: "cache-control"
			- Note: "no-cache" does not mean no caching
			- max-age, expiry
			- can specify whether revalidation required etc.
		- E-Tag: Entity tag header
			- Unique ID for a resource: cache can identify
		- Freshness checking – estimating freshness in absence of Expires
		- Explicit versions on resources
	- Is caching bad for website popularity?
		- reduces hits on server
		- traffic goes to cache / proxy instead of server
		- Bad way to approach the problem:
			- not all hits should be on server: cache as much as possible
			- use indirect approaches like analytics to update / track visitors
	- ##### Flask Caching
		- Module that integrates directly with Flask
		```python
		@app.route("/")
		@cache.cached(timeout=50)
		def index():
			return render_template('index.html')
		```
	- Cache Key
		- Cache <=> Python Dictionary
		- Key –> Value
		- View functions: Key – request path (route)
		- Non-view functions example:
			```python
			@cache.cached(timeout=50, key_prefix='all_comments')
			def get_all_comments():
				comments = do_serious_dbio()
				return [x.authore for x in comments]
			
			cached_comments = get_all_comments()
			```
	- <u>Memoization</u>
		- Memo: note to be remembered
		- Memoize: create a note (cache entry) based on some function arguments
		- without function arguments, same as 'cached'
		- example
			```python
			class Person(db.Model):
				@cache.memoize(50)
				def has_membership(self, role_id):
					return Group.query
								.filter_by(user=self, role_id=role_id)
								.count() >= 1
			```
	- Jinja caching
		```html
		{% cache 60*5 %}
		<div>
			<form>
			{% render_form_field(form.username) %}
			{% render_submit() %}
			</form>
		</div>
		{% endcache %}
		```
	- Caching backends
		- NullCache: don't cache – just for testing
		- SimpleCache: Local Python dictionary – not thread sage
		- FileSystemCache: store to files on disk
		- RedisCache (and variants):
			- store in Redis key-value
			- requires separate Redis instance, possible to reuse same server Celery etc.

- ### Screencast
	- [link](https://www.youtube.com/watch?v=Ggn1nTH2Srg&ab_channel=IITMadras-B.S.DegreeProgramme)

# <u>Week 12</u>
- ### Frontend Security
	- ##### Cookies
		- Session vs Permanent
			- Logging in and using sites
			- Automatically activated by browser
			- GDPR led to the "This site uses cookies" banners
		- First-party vs Third-party
			- Directly from site: used for logins, session information, user preferences
			- Third-party: usually from advertisers, only peripherally related to site visited, blocked by most major browsers now due to privacy concerns
	- ###### Cross-site scripting (XSS)
		- example: enter data in a query field without validation
			- GET \http://example.com/help?q=message
			- Output: "<\p>message<\/p>"
		- Could store the malicious code in the site database (forum posts, blog comments, etc.)
		- Server side: validation to prevent injection of attack
		- Client side: prevent automatic cross-site script loading
	- ###### Cross-site Request Forgery (CSRF)
		- example:
			- you log into your bank account and have an active session
			- you open another tab and go to an attacker page and click on a link
			- how can the bank differentiate between you clicked in the correct tab vs in the attackers tab?
		- CSRF Tokens: Secure token created only through application, limited validity lifetime
	- ###### Cross-Origin Resource Sharing (CORS)
		- Reduce chances of malicious code by explicitly saying which URLs can be originators of data
		- API server allows www to make requests on user behalf
- ### Backend Security
	- ##### Package management issues
		- Flask application uses other libraries
			- requests, google APIs, markdown
			- requirements.txt used to specify libraries
		- version of libraries pinning
	- Problem with Log4j
		- a very common library
			- excellent features, well supported
			- had a bug since 2013
		- faker.js module used to testing JS code
			- abruptly replaced with black code – breaking all modules using it
	- Avoiding supply chain issues
		- Reduce dependencies – not always possible, but should be attempted
		- Version pinning – ensure exact version of dependencies specified
		- Keep up to date with security issues
	- ##### Server communication
		- Endpoint security – server maintenance
		- End-to-end encryption
			- TLS
			- HTTPS is equivalent for browser-server, but server-server should also be secure
		- Authorised communication
			- Only accept requests from known clients (frontend servers) to backend
			- Network level filtering where possible
	- ##### Denial of Service
		- Attack that doesn't try to leak information
		- Just bring down the server and make it unavailable
		- Very problematic for high traffic sites: even few seconds has big impact
		- Distributed Denial of Service – Large scale attacks; ISP level protections needed
	- ##### App deployment
		- Automate
		- SSH access – No un-encrypted access at all
		- Secret token management – vaults, environment variables should not be in version control
		- Secure database access
	- ##### Logging
		- Logs essential in case of problem-backtrace
		- Too much logging can affect performance, costs
		- Balance between performance and debuggability
		- Regular sumaries from logs should be stored
		- Rotate logs to avoid unnecessary growth

- ### Screencast
	- [CORS and Cookies](https://www.youtube.com/watch?v=RtcdLbcfMkY&ab_channel=IITMadras-B.S.DegreeProgramme)
