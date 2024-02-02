
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
- 