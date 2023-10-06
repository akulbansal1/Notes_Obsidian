
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
	- protocol: how to format packets; place them on wire. Each network had its own protocol
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
- **HTTP**: Hyper Text Transfer Protocol: how the client should talk to a server and how the serve should respond.
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

- Latency: how much time it takes to get a response for a given request
	- 5 nanoseconds per meter; 5 millisecond for 1000 kilometer
	- if data center is 2000km away, then round-trip latency is 20ms; limited to 50 requests per second
- Response size
	- 1 kilobyte of text; if network connection = 100 megabits per second Mbps; 100 Mbps ~ 10 MBytes/s; then you're limited to 10,000 requests per second
	- Google's page content gives 144kB content; and it receives 60,000 requests per second. $$144 \cdot 60,000 = 8,640,000 kiloBytes/s$$ which is equal to 86,000,000 Kbps = 86 Gbps. Google's servers need 80 Gbps bandwidth.

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
- Responsive Design:
	- Adapt to the screen (phone, tablet, etc.) — *Respond*
- Bootstrap
	- commonly used framework - originated from Twitter
	- Standard styles for various components: buttons, forms, icons
	- mobile first: highly responsive layout

<!DOCTYPE html>
<html lang="en">
	<head>
		<title>Document</title>
			<style>
				body {
					color: red;
					color: green;
					color: yellow;
					}
			</style>
	</head>
	<body>
		IIT Madras
	</body>
</html>