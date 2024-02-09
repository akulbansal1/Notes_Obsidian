
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