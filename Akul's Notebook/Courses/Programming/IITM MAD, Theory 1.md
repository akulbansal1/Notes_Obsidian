
# <u>Week 1</u>

- ##### Components of an App:
	1. Storage
	2. Computation
	3. Presentation
- ##### Platforms
	- Desktop
	- Mobile
	- Web-based (focus of this course)
	- Embedded: single function; limited scope
		- e.g. watch app on your phone, electronic calculator, etc.
- ##### Architecture:
	1. Client-Server
		- Server: stores data; provides data on demand; may perform computations
		- Clients: end users; request data; UI display
		- Network: connects client to server; can be local; data pipe (no alterations)
		- Explicit differentiation between clients and servers
		- examples: email, databases, whatsapp / messaging, web browsing, etc.
	2. Distributed (Peer-to-Peer)
		- no differentiation between client and servers. All peers are considered 'equivalent' but some peers are more equal than others
		- examples: Bittorrent; blockchain-based systems
- ##### Software Architecture Patterns:
	- M-V-C paradigm:
		- Model: core data to be stored for the app; databases; indexing for easy searching, manipulation
		- View: user-facing side of app; interfaces for finding information, manipulating
		- Controller: business logic - how to manipulate data
		- User uses **controller** to manipulate **model** that updates **view** that user sees.

- ##### Web:
	- platform of choice for this course
	- works across operating systems, hardware architectures
	- protocol: how to format packets; place them on wire. Each network has its own protocol
	- IP: Internet Protocol: defines headers, packet types, interpretation; can be carried over different underlying networks
	- TCP: Transmission Control Protocol: establish reliable communications; error control. Automatically scale and adjust to network limits
	- Domain names: use names instead of IP addresses; e.g. Apple.com will refer to some IP address that will take you to the machine hosted by the Apple company.
	- World Wide Web is a system of interconnected resources over the internet.
	- Internet is a network of networks.
	- Web 2.0 ~ 2004+
		- dynamic pages
		- HTTP as a transport mechanism - binary data; serialised objects
		- platform agnostic operating system

- Web server
	- any computer with a network connection
		- as simple as running a small piece of software
	- software:
		- **takes a request**: listens for incoming network connections on a fixed port (usually a number between 1 and 65,000)
		- respond in specific ways
	- protocol:
		- how to communicate between two devices; formatting
		- how should server respond to client
- **HTTP**: Hyper Text Transfer Protocol: how the client should talk to a server and how the server should respond.
	- HyperText: regular text document; contains codes inside that indicate special function - how to 'link' to other documents. [This is a HyperText](https://www.google.com/)
	- HTTP: client send requests, server responds with hypertext document
	- requests specified as "GET", "POST", "PUT" etc.
		- header can be used to convey acceptable response types, languages, encoding
		- which host to connect to (if multiple hosts)
		- status code (300 error codes): "200 OK";  "404 not found"; "500" server crashed
	- GET: simple requests, search queries, etc.
	- POST: more complex form data, large text block, file uploads
	- PUT/DELETE/... : rarely used in Web 1.0; extensively used in Web 2.0; basis of most APIs - REST, CRUD

- Simplest possible web server
	```Shell script
	while true; do
		echo -e "HTTP/1.1 200 OK\n\n $(date)" |
			nc -1 localhost 1500;
	done
	```
	- "|" --> pipe symbol; do something with line 1 and pipe that info into line 2
	- "echo -e" prints out the the following text 
	- "nc" --> netcat and nc is going to listen to on localhost, i.e., the local server port number 1500

- Another web server
	```
	python -m http.server
	```
	- "index.html" file is the output you get when you "curl" this server

- <u>Latency</u>: how much time it takes to get a response for a given request
	- 5 nanoseconds per meter; 5 millisecond for 1000 kilometer
	- if data center is 2000km away, then round-trip latency is 20ms; limited to 50 requests per second
- Response size
	- 1 kilobyte of text; if network connection = 100 megabits per second Mbps; 100 Mbps ~ 10 MBytes/s; then you're limited to 10,000 requests per second
	- Google's page content gives 144kB content; and it receives 60,000 requests per second. $$144 \cdot 60,000 = 8,640,000\ \text{kiloBytes/s}$$ which is equal to 86,000,000 Kbps = 86 Gbps. Google's servers need 80 Gbps bandwidth.

# <u>Week 2</u>
- ##### Markup
	- controls how something gets displayed on the screen.
	- "a way of using cues or codes in the regular flow of text to indicate how text should be displayed"
	- deals with the aesthetics
	- HTML5 and CSS
	- LaTeX is a form of markup
	- **Types of Markup**:
		1. <u>Presentational</u>: WYSIWYG (What You See Is What You Get); MS Word; Google Docs, etc.
		2. <u>Procedural</u>: details on how to display: change font to large, skip 2 lines, indent 4 columns
		3. <u>Descriptive</u>: focuses on what it means. This is a \<title>, this is a \<heading>, this is a \<paragraph>
			- LaTeX, HTML
			- more complex to write and edit
- **Information representation**
	- "bits" $\to$ binary digits (0  and 1)
- Respresenting Text:
	- ASCII: 7-bits: 128 different entities $\to$ 'a'..'z'; 'A'..'Z'; '0'..'9'; special characters !@#$%^&*()..
	- Unicode: "Universal Character Set" encoding - UCS
		- UCS-2: 2 bytes per character $\to$ max $2^{16} = 65,536$ characters
		- UCS-4: 4 bytes per character $\to$ 4 Billion+ characters
- UTF-8: most common encoding in use today
	- uses 8 bits for most common characters: ASCII subset
	- most websites today have a meta tag which mentions that the character set being used is UTF-8

- ##### HTML
	- mean primarily for browsers; best effort to display
	- example:![[Screenshot 2023-10-01 at 1.59.51 PM.png]]
	- Nesting:
		- \<em>\<strong>Hello\</strong>\</em> $\leadsto$ <em><strong>Hello</strong></em>
	- \<strong>Hello\</strong> $=$ \<b>Hello\</b> $=$ <b>Hello</b>
	- Block elements: \<div>
	- Inline elements: \<span>
	- Logical elements: \<nav>, \<footer>
	- Media: \<audio>, \<video>
	- Document Object Model![[Screenshot 2023-10-01 at 2.16.30 PM.png]]

- ##### CSS (Cascading Style Sheets)
	- Styling allows you to show 'themes'
	- mention the styling in a tag
	- to use the same styling for multiple tags: embed the style in \<head> tag![[Screenshot 2023-10-01 at 2.48.20 PM.png]]adding this in the \<head> tag will make all the h1 tags look the same and all the body tags look the same.
	- Style precedence:
		- inline >> internal >> external
		- !important >> id >> class >> element
- Responsive Design:
	- Adapt to the screen (phone, tablet, etc.) — *Respond*
- Bootstrap
	- commonly used framework - originated from Twitter
	- Standard styles for various components: buttons, forms, icons
	- mobile first: highly responsive layout

# <u>Week 3</u>
- M-V-C paradigm:
	- Model: application object
	- View: screen representation
	- Controller: how user interface reacts to user input
	- User uses **controller** to manipulate **model** that updates **view** that user sees.
- MVC Controller:
	- origins: Smalltalk-80
	- roots in Object-Oriented GUI development

- ### **View**
	- User Interface: what you see
		- screen; audio; vibration
	- User Interaction: how you interact
		- keyboard/mouse; touchscreen; spoken voice; custom buttons
		- determined by hardware constraints
		- user-agent information useful to identify context (so that the server can adapt)
		- may not be under designer control
	- Types of views
		1. Fully static. Google.com is largely static.
		2. Partly dynamic. Wikipedia's page is not fully static (there is a lot of static text) but there are things like news/featured article that are dynamic.
		3. Mostly Dynamic. Amazon's page is pretty much dynamic (the page/text might be different at times)
	- Output
		- HTML - most commonly used - direct rendering
		- Dynamic images
		- JSON / XML - machine readable
	- ##### User Interface Design
		- `make sure to go through the reading material provided`
		- Goals: 1. **Simple** (easy to use); 2. **Efficient** (user's minimal effort)
		- Aesthetics: CSS libraries like bootstrap is very useful.
		- Accessibility: usually a conflict b/w aesthetic and accessibility
		- Systematic process: (steps)
			1. Functionality requirements - what is needed by the user?
			2. User and Task analysis - user preferences, task needs
			3. Prototyping - wireframes, mockups
			4. Testing - user acceptance, usability, accessibility
		- Guidelines/Heuristics: [[10 Usability Heuristics for User Interface Design|Jakob Nielsen's heuristics for design]]
	- ##### Tools
		- **Wireframes**
			- visual guide to represent structure
			- information design
			- navigation design
			- User interface design
			- example: [LucidChart](https://www.lucidchart.com/pages/examples/wireframe_software)
		- **HTML generations**
			- PyHTML
			```Python
			import pyhtml as h
			
			t= h.html(
				h.head(
					h.title('Test page')
				),
				h.body(
					h.h1('This is a title'),
					h.div('This is some text'),
					h.div(h.h2('inside title'),
						h.p('some text in a paragraph'))
				)
			)
			print(t.render())
			```
		- Templates
			- standard template text
			- we will be using "Flask", works well with Jinja framework
			```Python
			from string import Template
			
			t= Template('$name is the $job of $company')
			s = t.substitute(name="Tim Cook", job="CEO", company="Apple Inc.")
			print(s)
			```
		- Jinja
			```Python
			from jinja2 import Template
			t = Template("Hello {{something}}!")
			print(t.render(something="World"))
			
			t = Template("numbers from 1 to 9 are: {% for n in range(1,10) %}{{n}}" "{% endfor %}")
			print(t.render())
			```
	- **Accessibility**
		- Perceivable
			- provide text-alternatives
			- provide captions for multimedia
			- create content that can be presented in different ways
			- make it easier to users to see and hear
		- Operable
			- make all functionality available from a keyboard
			- give users enough time to read
			- do not use content that causes seizures
			- help users navigate and find content
		- Understandable
			- make text readable
			- content should appear in predictable ways 
			- help users avoid and correct mistakes
		- Robust
			- maximise compatibility with current and future user tools


# <u>Week 4</u>
- ##### Persistent Storage
	- Spreadsheets: 
		- organised into rows, and column
		- operations on cells and ranges
		- good for tabular data
	- CSV: comma separated values; TSV: tab separated values
		- limited flexibility
	- Relational Databases - SQL
		- data stored in tabular format
		- defined schema
		- columns: fields
		- rows: individual entries
	- Unstructured Databases - NoSQL
		- easily add/change fields
		- arbitrary data
		- examples: MongoDB; CouchDB
		- flexible, but potential loss of validation

	- Relationship (between datasets) types:
		- **One-to-one**
			- One student has one roll number; roll no. uniquely identifies one student
			- Every e-mail in the Inbox has a unique message-ID
		- **One-to-many**
			- One student stays in one hostel; one hostel has many students
			- One e-mail is only in one folder; multiple e-mails in a single folder
		- **Many-to-many**
			- One student can register for multiple courses; one course can be taken by many students
			- One e-mail can have many labels; and a single label can have many e-mails
	- **Entity-Relationship (ER Diagrams)**
		- showing a relationship between entity A and entity B![[Screenshot 2023-10-15 at 2.08.31 PM.png]]
		- Example for an e-commerce website.
		  One customer may have 0 or many orders; one order must have one and only one customer.
		  One shipment must be from one and only one order; an order may have 0 or many shipments![[Screenshot 2023-10-15 at 2.13.55 PM.png]]
	- Tools: [Draw.io](https://app.diagrams.net/)

# <u>Week 5</u>
- Originally for GUI applications
- Model-View-Controller: Design pattern - or collection of design pattern![[Screenshot 2023-10-22 at 2.53.04 PM.png]]
- <u>Models</u>:
	- represents knowledge; either about a single object or could be some structure of objects.
- <u>Views:</u>
	- visual representation of the model; acts as a *presentation filter*.
- <u>Controllers:</u>
	- link b/w user and system.
	- provides the user with input.
	- controller shouldn't supplement the views; don't let the controller edit the views.
- Web:
	- server and the client are on different machines, i.e., server cannot know the state of the client.
	- client is pure front-end to user.

##### CRUD
- Types of operations: CREATE — READ — UPDATE — DELETE
	- Create:
		- create a new entry
		- must not already exist
		- check within database to avoid conflicts
		- mention mandatory vs. optional fields
	- Read:
		- list of students
		- summarise data
		- plot
	- Update:
		- updation in the data
	- Delete:
		- delete mistaken entries
		- un-enroll students
- Originally in context of database; reflects the life-cycle of data models
- Databases optimised for various combinations of operations
	- read-heavy
	- write-heavy

### API (Application Programming Interface)
- In the context of the Web, we take the concept of CRUD and then cast that in the form of an API
- Standardised way of communicating with a server.
- Client only needs to know the API, not how the server implements the database.
- In the case of the web, the communication b/w client and server is happening through HTTP protocol.

#### Controller
- CRUD etc are a set of actions; and other actions
- each of these actions can be thought of as a controller![[Screenshot 2023-10-22 at 6.59.18 PM.png]]
- Actions: interaction b/w view and model
- Controller groups actions together logically
- API: complex set of capabilities of server
- Web Applications: interaction through HTTP requests; HTTP Verbs used to convey meanings

<u>Rules of thumb</u>
- should be possible to change views without the model knowing
- should be possible to change the underlying storage of model without views every knowing
- controllers/actions should generally never talk to a database directly; that is the model's job

#### Web Applications
- Requests sent through HTTP protocol
	- Use variants of the GET, POST (Verbs) to convey meaning
	- Use URL (Uniform Resource Locator) structure to convey context

Python Decorators: add extra functionality on top of a function
- "@" - decorators before function name 
- Effectively function of a function


# <u>Week 6</u>
- ## API
	- REpresentational State Transfer and Application Programming Interfaces 
	- any application is a <u>Distributed Software Architecture</u>
		- Server-clients; standard 'protocols' needed for communication
		- Assumptions? server always on? client authentication? network latency?
	- Web app:
		- client-server are far apart
		- different networks, latencies, quality
		- Authentication? Not core part of protocol
		- State?
			- Server doesn't know about client-state
			- Client can't be sure about server-state
- Architecture for the Web:
	- Roy Fielding. REST
	- REST takes into account limitations of the web as a platform
	- provides guidelines/constraints

- ## REST
	- ##### Constraints:
		1. <u>Client-Server</u>![[Screenshot 2023-11-04 at 11.17.04 PM.png]]
		2. <u>Stateless</u>
			- Server cannot assume state of client: which page are you looking at, etc.
			- Client cannot assume state of server: did server reboot since last request, is the request being answered by same server, etc.
		3. <u>Layered System</u>
			- As far as the client is concerned, it doesn't know where the response is coming from, just that the response came from somewhere in the network.
			- Load Balancer - doesn't do any computations. Only keeps track of which of the servers is free to handle a request.![[Screenshot 2023-11-04 at 11.19.05 PM.png]]
		4. <u>Cacheability</u>
			- Cache: temporary storage.
			- Front-end stores some data without having to go backend server.![[Screenshot 2023-11-04 at 11.24.06 PM.png]]
		5. <u>Uniform Interface</u>
			- Client and server interact in a uniform and predictable manner.
			- Server exposes 'resources' and a standardised way of interacting with those resources.
		6. Code on Demand
			- Server can extend client functionality
	- State information between client and server explicitly transferred with every communication.
	- Typical <u>Sequence</u> of a REST-based communication
		- Client access a resource identifier from server: usually URI – superset of URL; start from home page; no initial state
		- Resource operation specified as part of access: If HTTP, then GET, POST, etc.; not fundamentally tied to protocol
		- Server responds with new Resource Identifier: new state of system; new links to follow; etc.
	- ##### HTTP:
		- one possible protocol to carry REST messages
		- GET: retrieve representation of target resource's state
		- POST: enclose data in request: target resource 'processes' it
		- PUT: create a target resource with data enclosed
		- DELETE: delete the target resource
	- <u>Idempotent operations</u>
		- repeated application of operation is not a problem
		- example: GET is always safe: read-only operation
		- example: PUT will always create the same new resource; if already exists, may give error
		- example: DELETE can delete only once; maybe error on repeated deletion but won't change the data
		- <u>POST is NOT idempotent</u> (create or update)
			- example: add comment to blog - repeat will cause multiple copies.

- ## CRUD
	- Create-Read-Update-Delete
	- database operations
	- are usually implemented using REST-based functionality
	- can use notions of REST in order to implement CRUD
	- CRUD != REST: CRUD applies to the database; REST applies to the architecture of the web application

- Data Encoding
	- HTML: for simple responses
	- XML: structures data response; more extensible than HTML; difficult to edit/write
	- JSON: Java Script Object Notation: simpler form of structured data

- ## JSON
	- Java Script Object Notation
	- example: let's say the Controller doesn't want to get back an HTML file. Controller only want the data which can be fed into a View
	- Nested arrays: serialise complex data structures like dictionaries, arrays, etc.![[Screenshot 2023-11-04 at 11.50.55 PM.png]]

- API data transfer format
	- Input: text – HTTP 
	- Output: HTML or complex data types (JSON, XML, YAML, etc.)
	- different from internal server representation
	- different from final view presentation
	- YAML: Yet Another Markup Language — common alternative; primarily used for documentation and configuration

## REST APIs
- typical functionality:
	- CRUD (data management)
	- variants of listing
- REST plays a part in the way by which the data is transferred b/w the model and the controller
- <u>Example: Wikipedia</u>
	- open API
	- search pages
	- history of page
	- JSON output
	- `w/rest.php` says it's taking you to the REST API rather than to something that'll give HTML page; JSON output
	  `v1` is the API version
	  `search/page` is the resource you're activating (functionality) with parameters: `q=` string  ![[Screenshot 2023-11-05 at 12.06.10 AM.png]]

- ### OpenAPI
	- APIs for web apps:
		- purpose: information hiding - neither server not client should know details of implementation on other side
		- unbreakable contract: should not change - standardised
	- Description Files
		- machine readable - specific structure; example: XML
		- enable automated processing: boilerplate code; mock servers
		- example: assembly language is a version of the programming language of computers that is both machine and human readable
	- ### OpenAPI Specification (OAS)
		- Vendor-neutral format for HTTP-based remote API
		- does not aim to describe all possible APIs
		- originally developed as Swagger - evolved from Swagger 2.0

- ## Important concepts of API
	- Specification file for an API 
		- mostly done in YAML (or in JSON)
		- should be machine-readable
		- example:![[Screenshot 2023-11-05 at 12.26.20 PM.png]]
	- Endpoints
		- paths in the OpenAPI object contains paths object will have multiple endpoints.
		- Endpoint: URL that you're going to access.
		- Operation that you're going to perform combined with the URL will give specific behaviours.
	- Structure of an OpenAPI specification document ![[Screenshot 2023-11-05 at 12.27.27 PM.png]]
	- YAML specification doc:
		- <u>Example</u>![[Screenshot 2023-11-05 at 12.34.42 PM.png]]Operations:![[Screenshot 2023-11-05 at 12.35.32 PM.png]]Operation object![[Screenshot 2023-11-05 at 12.36.36 PM.png]]
		  Response object![[Screenshot 2023-11-05 at 12.37.32 PM.png]]Content Specification: as part of API, you can request different formats of data. controller can then choose which view to return. server doesn't need to know.![[Screenshot 2023-11-05 at 12.38.56 PM.png]]Schema for content![[Screenshot 2023-11-05 at 12.40.26 PM.png]]Path can specify parameters![[Screenshot 2023-11-05 at 12.41.54 PM.png]]

- ## Best practices
	- Design-first vs Code-first
	- Single source of truth:
		- structure of code should be derived from OAS (OpenApiSpecification)
		- minimise chances of code and documentation diverging
	- Source code version control
	- OpenAPI: meant to be public; documentation better to identify problems
	- automated tools, editors for YAML.

## LAB 6:
- editor.swagger for API documentation in YAML.
- Used mermaid.live to insert an image for an ER diagram.
- use swagger for viewing YAML files.

# <u>Week 7</u>
- ##### Memory Hierarchy
	- types of storage elements: 
		- on-chip registers: 10s - 100s of bytes; pretty small in number
		- SRAM (cache): 0.1 - 1 MB; limited in capacity; temporary store of data; access speed is much faster
		- DRAM: 0.1 - 10 GB
		- Solid-state disk (SSD): 1 - 100 GB; using flash-based tech
		- Magnetic disk (HDD): 0.1 - 10 TB
	- Latency (time to read the first value; lower is better): Register < SRAM < DRAM < SSD < HDD
	- Throughput (number of bytes/second than can be read; higher is better): DRAM > SSD > HDD
	- Density (number of bits stored per unit area/cost; higher is better): HDD > SSD > DRAM > SRAM > Reg
- Index-friendly query:
	- `SELECT * FROM tabl_name WHERE key_col LIKE 'Patrick%'`
	- `SELECT * FROM tabl_name WHERE key_col LIKE 'Pat%_ck%'`
- Index-<u>un</u>friendly query:
	- `SELECT * FROM tabl_name WHERE key_col LIKE '%Patrick%'`
	- `SELECT * FROM tabl_name WHERE key_col LIKE other_col`
- Multi-column index
	- (index_1, index_2, index_3): compound index on 3 columns: will sort on index_1, then on index_2, then on index_3
- Hash index
	- only used in in-memory tables
	- only for equality comparison; cannot handle range 
	- does not help with 'ORDER BY'
	- partial key prefix cannot be used
	- is very fast

- <u>SQL: Structure Query Language</u>
	- structured databases
	- RDBMS - columns/fields
		- all entries must have same set of columns
- <u>Document databases</u>
	- free-from (unstructured data); each document has its own structure
	- typically JSON encoded
	- examples: MongoDB, Amazon DocumentDB
- Key-value
	- dictionary, or hash table
	- efficient for key lookup but not for range type queries
	- examples: Redis, BerkelyDB, memcached
- Column store
	- retrieve all values of an attribute very fast
	- examples: Cassandra, HBase
- Graph
	- social networks, maps
	- different degrees, weights of edges, nodes, etc.
	- path-finding more important than just search
	- examples: Neo4J, Amazon Neptune
- Time Series
	- used for log analysis, performance analysis, monitoring.
	- typically RDBMS are unsuitable
	- examples: RRDTool, InfluxDB, Prometheus

- ACID
	- <u>Atomic</u>: an operation should be atomic, either the entire user entry was created or the database is unchanged
	- <u>Consistent</u>: no two copies of database have different information
	- <u>Isolated</u>: one series of transactions should not interfere with another series of transactions
	- <u>Durable</u>: gets saved to a permanent storage

- <u>Redundancy</u>:
	- multiple copies of data
	- used in connection of backups
	- one copy is still the master
- <u>Replication</u>
	- used in context of performance
	- multiple sources of same data --> less chance of server overload
	- live replication requires careful design
- BASE
	- Basically Available, Soft state, Eventually consistent
	- high availability > consistency
- Replication of traditional DBs
	- RDBMS replication possible
	- usually server cluster in same data center
	- geographically distributed replication is harder
- Scale-up: traditional approach
	- larger machine, more RAM, faster network, processor
	- requires machine restart with each scale change
- Scale-out:
	- multiple servers, harder to enforce consistency
	- better suited to cloud model
	- better suited for NoSQL / Non-ACID

- Validation of inputs from a form must be done before the database query
- Web App security
	- use known frameworks, validation when doing SQL injection
- HTTPS:
	- secure sockets: secure communication between server and client
	- server certificate: very difficult to spoof; based on mathematical properties
	- Only secures link but does not perform validation 


# <u>Week 8</u>
- Application front-end
	- user-facing interface
	- Device/OS specific controls and interfaces
	- browser vs native: look and feel; API, interfaces, interaction
- Web applications frontend mechanism:
	- how to generate HTML, CSS, JS?
	- functional reuse, common frameworks 
	- server/client load implications
- ##### Fully Static pages
	- statically generated: compiled ahead of time
	- excellent for high performance (server just picks up file and delivers)
- ##### Run-time HTML generation
	- traditional CGI/WSGI based apps (python flask and django)
	- great flexibility: common layouts, adaptation and theming easy
	- every page has to be generated dynamically so higher server load
- Client-side scripting: Javascript de facto standard
- Asynchronous updates
	- update only part of the page instead of rendering the entire page every time.
	- requires a <u>Document Object Model</u>
		- programming interface for web documents
		- abstract model (tree structure) of the document
		- object-oriented allows manipulation
		- tightly couples with Javascript
		- example:![[Screenshot 2023-11-12 at 1.38.18 PM.png]]
		- manipulating the DOM![[Screenshot 2023-11-12 at 1.39.56 PM.png]]
- Accessibility: pages should not rely on colours or font sizes/styles to convey meaning
- JavaScript engines:
	- Chrome/Edge: V8
	- Firefox: SpiderMonkey
	- Safari, older versions os IE use their own
- JavaScript uses client CPU power (or GPU)
	- potential to load CPU
- machine end-points: typically access APIs
	- typically cannot handle JS - only HTTP endpoints
- Alternative scripting language: <u>Brython</u>
	- Javascript interprets the python code
- Usual approach to look for alternative scripting language: Transpilation (translation - compilation)
- WASM (Web Assembly): executable format for the web
	- handles high performance execution
	- Emscripten complier framework: compile C or C++ to WebAssembly
- Native Mode
	- web application behave like a desktop application

- #### Validation
	- Server-side validation is essential
	- Inbuilt HTML5 form controls:
		- required: mandatory field
		- minlength, maxlength: for text fields
		- min, max for numeric values
		- type: for specific predefined types
	- Javascript contraint validation API
	- Sandboxing: secure area that JS engine has access to; cannot access, network resources, and local storage.
	- Overload and DoS:
		- server attack: replace popular JS file with a bad version; will be loaded by large number of sites, users - can write script to access some other site
	- giving JS native access will give it access to recourses like local storage, sensors

# <u>Week 9</u>
- #### Access Control
	- types of access:
		- read-only
		- read-write (CRUD)
		- modify but not create
	- <u>Discretionary</u>: left to the user's discretion; can change the permissions
	- <u>Mandatory</u>: if you have access to something doesn't mean you can pass that access to someone else
	- role-based access control
	- attribute-based access control (example: time of day, some attribute of user)
	- Permissions: static rules based on simple checks
	- Policies: more complex conditions possible; combine multiple policies
	- Entity should have minimal access required to do the job
		- better <u>security</u>
		- better <u>stability</u>
		- ease of <u>deployment</u>
	- Privilege escalation ('sudo' in Linux)
		- usually combined with explicit logging, extra safety measures
	- <u>Enforcing</u>
		- Hardware Level 
		- Operating system (filesystem access, memory segmentation)
		- Application level (DB server can restrict access to specific database)
		- <u>Web Application</u> (controllers enforce restrictions; decorators in Python)

- #### Security Mechanisms
	- Types of security checks
		- <u>Obscurity</u>: application listens on non-standard port known only to specific people
		- <u>Address</u>: server will check which IP address you're coming from; host-based access control
		- <u>Login</u>: username/password provided to each person needing access
		- <u>Tokens</u>: access tokens that are difficult/impossible to duplicate; can be used for machine-to-machine authentication without passwords
	- HTTP authentication
		- ##### Basic: 
			- enforced by server
			- Error 401: Unauthorised code to client
			- 404: not found
			- 403: forbidden
			- client must respond with <u>access token</u>
			- problems: username/password effectively sent as plain text; password will be seen in cleartext at server; no standard process for 'logout'
		- ##### Digest authentication: (cryptography)
			- use mathematical functions/properties to say that certain kinds of operations are going to be very difficult to perform
			- One-way function: $f(A)=B$    easy to compute $B$ given $A$ but near impossible to compute $A$ given $B$
			- can define one-way function on strings: string $\to$ binary number
			- NONCE (number used once)
			- Client must create a secret value including nonce
			- Server and client know all parameters
			- any third party snooping will see only final response
		- ##### Client certificates
			- cryptographically secure certificates provided to each client
			- keep cert secure on client end: impossible to reverse and find the key
		- Form input
			- GET requests are insecure, open to spoofing; get logged
			- POST requests: slightly more secure; still needs secure link to avoid data leak
		-  Request level security
			- One TCP connection: one security check is sufficient
			- without connect KeepAlive: each request needs new TCP connection; each request needs new authentication
		- Cookies
			- random piece of information which the server sends back to the client
			- Server checks some client credentials, then 'sets a cookie'
			- client must send back the cookie with each request
			- server maintains 'sessions' for clients: remember cookies; can set timeouts; delete cookie records to 'logout'
		- API security
			- use 'token' or 'API key' for access

- #### Sessions
	- server needs to have 'state' information and customise response based on client session information
	- Storage:
		- Client-side session: completely stored in cookie
		- Server-side session: stored on server, looked up from cookie
	- Cookie:
		- set by server with Set-Cookie header
		- can be used to store information: theme, background colour; user permissions, username (must not be possible to alter)
		- Example in Flask![[Screenshot 2023-11-24 at 9.13.53 PM.png]]![[Screenshot 2023-11-24 at 9.15.41 PM.png]]
		- if someone else gets Cookie, they can log in as user
	- Server-side information
		- maintain client information at server
		- not easy to alter
		- requires persistent storage at server
		- multiple backends possible: file storage; database; redis, or other caching key-values stores
	- Enforce authentication:
		- HOW: existence of specific token for access to those views
		- VIEWS: determined by controller
		- Protect access to controller: protect function - add wrapper around it to check auth status (Decorator)
	- HTTP GET URLs not good: logged on firewalls, proxies, etc.
	- Use HTTP POST, Cookies

- #### HTTPS
	- Normal HTTP process:
		- Open connection to server on fixed network port
		- Transmit HTTP request
		- Receive HTTP response
		- Transmitted data: can be tapped/altered
	- Secure sockets
		- sets up an 'encrypted channel b/w client and server'
		- How: shared secret(long binary string); XOR all input data with key; attacker without key cannot derive actual data
		- set-up
			- assume anything on the wire can be tapped
			- secure side-channel – send a token by post, SMS
	- Types of security:
		- Channel (wire) security: ensure no one can tap the channel
		- Server authentication: how do we know we connected to the right server; server certificates
			- Common root of trust
		- Client certificate: rare but useful; better than using password; used in corporate intranets
		- Chain of trust: mail.google.com issued certificate by GTS CA1C3 issued certificate by GTS Root R1 certificate stored in Operating System or Browser. From there on a secure (crypto) chain
			- Potential Problem: Old browsers; stolen certificates at root of trust; DNS hijacking 
	- <u>Impact of HTTPS</u>:
		- security against wiretapping
		- better in public WiFi networks
		- negatives: performance due to run-time encryption; affects caching of resources (proxies cannot see content)

- #### Logging
	- Why
		- record bugs
		- statistics of usage pattern, visits, etc.
		- security checks
	- How
		- build into app – output to log file
		- direct output to analysis pipeline
	- ##### Server Logging
		- build into Apache, Nginx, etc.
		- it can only log information about which URL was being accessed
		- can indicate possible security attacks:
			- large number of request in short duration
			- requests with 'malformed' URLs
			- repeated requests to unusual endpoints
	- ##### Application Level Logging
		- Python logging framework
		- details of application process: which controllers; what data models; possible security issues
		- all server errors
	- Log rotation
		- make sure logs are kept to minimum; mostly written, less analysis
		- rotation: keep last $N$ files; delete oldest file; rename log.i to log.i+1
	- Time series analysis
		- logs are associated with timestamps
		- detect patterns: periodic spikes, sudden increase in load, etc.
		- time-series databases: RRDTool, InfluxDB, Prometheus, etc.

# <u>Week 10</u>
- ### Application Testing
	- #### Why?
		- does it work as intended?
		- requirements/specifications
		- respond correctly to inputs
		- respond within reasonable time
		- installation and environment
		- usability and correctness
	- #### Static vs. Dynamic
		- <u>Static</u>: code review; correctness proofs; not running the program
		- <u>Dynamic</u>: functional tests; apply suitable inputs
	- #### White-box testing
		- detailed knowledge of implementation
		- can examine internal variables, counters
		- tests can be created based on knowledge of internal structure
		- Pro: detailed information, better tests
		- Cons: focus on less important parts; does not encourage clean abstraction; too much info
	- #### Black-box testing
		- only interface available, not the code
		- Pros: closer to real usage scenario; encourages clean abstraction of interface
		- Cons: may miss obvious edge cases; debugging is harder
	- Grey-box testing
		- enforce interface as much as possible
		- internal structure mainly used for debugging, examining variables, etc.
	- #### Regressions
		- series of tests starting from basic development of code; each test for feature(s)
		- <u>regression</u>: loss of functionality introduced by some change in the code
		- future modifications to code should not break existing code
		- keeping a track of anything that has passed a test
	- #### Coverage
		- how much of the code is 'covered' by tests
			- every line executed at least once — 100% code coverage
			- <u>does not guarantee 'correctness' because of edge cases</u>
		- <u>branch coverage</u>: covers all exit routes of a bracnh
		- <u>condition coverage</u>: covers all possible outcomes of each condition
		- <u>function coverage</u>: functions are invoked at least once

- ### Levels of Testing
	- #### Initial requirements gathering
		- stakeholders? users, admins, etc.
		- functionality: each group of stakeholder has different needs
		- non-functional requirements: page color, font, etc.
		- extensive discussions with end-user 
		- capture use cases and *examples*
	- #### Unit Testing
		- break functional requirements down to small, implementable <i><u>units</u></i>
		- each one may become a single controller (may also combine multiple into a single controller)
		- test each individual unit
		- maybe a single controller (or a part of a controller)
		- clearly define inputs and expected outputs
		- testable in isolation?
	- #### Integration Testing
		- multiple modules in application
		- ultimately, all functions need to be integrated to get the complete application
		- potential problems: individual units work but combined system does not
		- continuous integration: combined with version control systems
	- #### System-level Testing
		- after integration testing
		- includes server, environment
		- mainly black-box: should validate final usage
		- browser automation framework (example: Selenium)
	- #### User Acceptance Testing
		- deploy final system
		- tested by restricted set of users - pilot
		- 'beta' testing (pre-production)

- #### Test Generation
	- #### API-based testing
		- API: abstraction for system design
		- standard APIs: OpenAPI, Swagger, etc.
		- Swagger Inspector: can generate tests for endpoints
	- ##### Use cases
		- import API definition
		- generate test for specific endpoints
		- record API traffic
		- inject possible problem cases based on known techniques
		- data validation tests
	- #### Abstract Test
		- semi-formal verbal description
		- example: Make a request to '/' endpoint and ensure that results contains text "Hello World"
	- Executable Test
		- coded test
		- example (previous abstract test codedin python): 
			```python
			def test_hello(client):
				"""Verify home page"""
				rv = client.get('/')
				assert b'Hello World' in rv
			```
	- #### Model-based testing
		- Think of entire software to be running a model of execution
		- example: authenticate user before showing info
			- scenarios: user already logged in - page shown; user not yet logged in - redirect to login; forgot password - after resetting, come back to desired page
			- <u>Model</u>: possible states (logged, password reset,...); possible transitions; generate tests for the possible transitions
		- usually combined with abstract tests
		- derive 'executable' tests by combining abstract test information with model
	- #### (G)UI Testing
		- user interface — visual output
		- usually GUI, even for web-based systems
		- Tests:
			- are the specific elements present on the page
			- are navigation links present
			- what happens on random click on some part of the page
		- ##### Browser automation
			- some tests require a browser
			- Selenium framework: allows you to directly automate a browser
	- #### Security Testing
		- generate invalid inputs to test app behaviour
		- try to crash server — overload, injection, etc.
		- Fuzzing or fuzz-testing:
			- generate large number of random/semi-random inputs

- ### PyTest
	- framework to make testing easier in Python
	- provides defaults to make it easier to write tests
	- features: automatically set up environment, tear down after test; test fixtures, monkey-patching (modifying code in order to run a test)
	- example: ![[Screenshot 2023-12-07 at 12.43.53 PM.png]]
	- ##### Test for exceptions
		- check if when the function `f()` is run, it raises an error `SystemExit`
			```python
			import pytest
			def f():
				raise SystemExit(1)
			
			def test_mytest():
				with pytest.raises(SystemExit):
					f()
			```
	- automatically create a temporary directory![[Screenshot 2023-12-07 at 12.49.58 PM.png]]
	- #### Test Fixtures
		- set up data before running a test and remove after test
		- example: initialise dummy database; create dummy users, files, etc.
		- example: 
			- `setup_list()` is decorated as a `pytest.ficture` ![[Screenshot 2023-12-07 at 12.52.57 PM.png]]
		- ###### Conventions
			- test discovery starts from current dir or `testpaths` variable
			- search for files name `test_*.py` or `*_test.py`
			- inside those files: any function that starts with `test` OR a method inside the class where the class name starts with `Test` and function starts with `test`
			- supports standard python `unittest` library

- #### Testing Flask applications
	- create a `client` fixtures known to Flask
	- set up dummy database, temp dir, etc. in fixture
	- user `requests` library to generate queries
	- <u>Example of Fixture setup</u>: `flaskr` is the name of the application that we're creating ![[Screenshot 2023-12-07 at 1.00.54 PM.png]]
	- <u>Example of Test</u>![[Screenshot 2023-12-07 at 1.04.08 PM.png]]
	- <u>Example of testing login and other features</u>![[Screenshot 2023-12-07 at 1.05.22 PM.png]]![[Screenshot 2023-12-07 at 1.06.47 PM.png]]

# <u>Week 11</u>
- #### HTML Evolution
	- Markup Languages
		- used for typesetting and document management systems
		- <u>problems</u>
			- lack of standardisation
			- target audience: coders, publishers, academics?
			- target output: print, other forms of media
			- machine readability
	- SGML
		- Standard Generalised Markup Language
		- meant to be a base from which any markup language could be designed
		- declarative: specify structure and attributes, not how to process
		- rigorous: strict definition of structure, like databases
		- DTD — Document Type Definition
			- to specify different families within this umbrella
			- each could have its own tags, interpretations
		- SGML *Applications*
	- HTML
		- originally intended HTML to be one specific application of SGML
		- very lenient with parsing – meant to be forgiving of errors
		- HTML 2.0 — attempt to become SGML compliant
		- HTML4 — true SGML application
		- HTML5 — no longer an SGML application, defines its own parsing rules
	- XML
		- eXtensible Markup Language
		- based on SGML
		- custom tags — multiple *applications* defined
		- allows arbitrary namespaces and tag definitions
		- focus on simplicity, generality and usability
		- human-readable and machine-readable
	- XHTML
		- based on XML – not directly SGML
		- reformulation of HTML4 
		- main goal: clean up HTML specification
	- HTML5
		- add support for latest features (multimedia, canvases, etc.)
		- easily readable and understandable by human and machine
		- remain backward compatible
		- break away from SGML
			- defines own parser

- ### JavaScript
	- High level language
		- dynamic typing
		- object orientation
	- Multi-paradigm
		- event-driven — respond to event. instead of just calling the function, what we say is 'if something happens, then call this function'
		- imperative — direct computation through procedures and functions
		- functional — composition of functions, functions as objects (define the equation and the interpreter figures out the best way to solve it)
	- Relatively easy to learn
		- similarities with python, C/C++, Java (no direct relationship)
	- ##### Why?
		- most web browsers have a dedicated engine just for running JavaScript
		- APIs:
			- Text, dates, regular expressions
			- DOM — manipulate the browser
			- no native IO (no file access, etc.) but provided through APIs
		- Most powerful when used for Document Object Model manipulation

- ### Web Component
	- Uses three aspects of HTML:
		- Custom elements (JS API to create custom element tags)
		- Shadow DOM (API to keep styling of component separate from the page)
		- HTML Templates (<\template> and <\slot> tags to write markup templates)
	- examples: [css-tricks](https://css-tricks.com/an-introduction-to-web-components/)
	- Custom Elements: API to extend HTML5 element/tag capabilities
	-  Shadow DOM: restrict scope of styling
	- HTML templates allow you to write reusable code

- ### Frameworks
	- Purpose:
		- basic functionality already available: Python can create network listeners, manipulate strings, etc. ; JS can extend elements, use APIs to manipulate documents
		- Problem: lots of code repetition
		- Solution: standard techniques for common problems — design patterns; frameworks: flask for Python web apps, React for JS components
		- SPA: Single Page Application
			- Many JS front-end framework focus on enabling this — also useful for mobile 
	- Example: React
		- library for building user interfaces
		- Declarative (specify what is needed, not how to do it)
		- Components
			- different from WebComponents
			- WebComponents are imperative; React is declarative 
		- example: [React](https://react.dev/)
	- Angular — origins from Google - well supported
	- EmberJS — component + service framework
	- Vue

# <u>Week 12</u>
- ### Components of an App
	- Permanent deployment
		- Dedicated servers
		- Always-on internet connection
		- Uninterrupted power
		- Infrastructure: data center via cloud
	- Scaling
		- multiple front-ends, each connected to every database server![[Screenshot 2023-12-19 at 1.19.16 PM.png]]
		- CDN (Content Delivery Network)
			- handing out static files

- ### Service Approach
	- Datacenter operators specialise in infrastructure
	- Developers focus on app development
	- ##### Software-as-a-Service (SaaS)
		- Online office platforms: Google docs, spreadsheets, Office 365
		- Content Management Systems: Drupal, Wordpress
		- Hosted solutions: all the software is installed and maintained
	- ##### Infrastructure-as-a-Service (IaaS)
		- Raw machines (or virtual machines)
		- Power, networking taken care of
		- Install your own OS
		- Cloud compute systems: AWS, Google Compute Engine, Azure, etc.
	- ##### Platform-as-a-Service (PaaS)
		- combination of hardware and software
		- hardware requirements: computing power, RAM, disk, etc.
		- software requirements: OS version, automated updates, firewalls
		- custom application code: Flask, RoR, Laravel
		- provider takes care of:
			- power, network
			- OS installation
			- base application platform: Python+Flask, PHP+Laravel: maintain multiple versions, manage security updates
			- multiple databases and connectivity options
		- developer needs to:
			- manage application  code
			- server sizing, database, connectivity
		- scaling: combined inputs from developer and provider
	- <u>Google App Engine</u>: (Platform provider, as opposed to Google Compute Engine)
		- web server front-end taken care of, various other things are automatically handled allowing you to focus on your code 
		- used for larger-scale projects, as opposed to Replit

- ### Deployment
	- Version Control
		- retain backups of old code
		- develop new features
		- fix bugs
	- Continuous Integration
		- Integrate with version control
		- Multiple authors contribute to different parts of code
		- Central 'build server' automatically compiles/builds code
		- **Automation is the key**
		- Test driven development (write tests before code)
		- Code review: pull and merge requests – enabled by web interfaces like github/gitlab; review code for correctness, cleanliness, etc.
		- Integration pipeline
			- tests run on each push to server – can be several times a day
			- fast runs, optimised based on changes, etc.
	- Continuous Delivery
		- once CI (testing) passed, package files for release
		- automated deliver of 'release package' on each successful test
	- Continuous Deployment
		- applicable more for web-based services
		- extend beyond delivery: deploy to production
		- passed tests -> deployed to users
			- users see latest version that has passed tests
			- no installing new versions
		- benefits
			- immediate fixes, upgrades
			- latest features deployed
		- drawbacks
			- tests many not catch all problems

- ### Containers
	- self-contained environment with OS and minimal libraries – just enough to run process
	- primarily used with Linux kernal namespaces
	- Why?
		- full OS impossible to version control
		- self-contained images that can be version controlled
		- Sandboxing – image cannot affect other processes on system
	- How?
		- Kernel level support needed
		- All communication 'inter-container' – networking
	- chroot
		- custom filesystem for part of the code
		- no real process isolation
	- FreeBSD jails, Linux VServer, OpenVZ
		- containers in Linux – same kernel, different filesystems
	- docker
		- mechanisms for managing images – popularised containers
- #### Orchestration
	- App consists of multiple processes (separate container for each process?)
	- Start in some specific order (dependencies)
	- Communicate between processes that are isolated (network)
	- Mechanisms to build and orchestrate, automate
		- docker-compose
		- Kubernetes
	- Key to understanding and managing large scale deployments

- App: Idea to deployment
	- Requirements $\to$ Tests $\to$ Code $\to$ Integration $\to$ Delivery $\to$ Deployment
	- Scaling
- Mechanisms
	- HTML + CSS + JS – Frontend user interface
	- Databases, NoSQL, cloud sotres – backend
	- Authentication, proxying, load balancing – "middleware"
	- Platform-as-a-Service – deployment and change management