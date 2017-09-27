# HTML5-Interview-Questions

If the DOCTYPE is not specified then the HTML tags will not be interpreted by the browser

Key goals and motivations for HTML5
====================================
1. Deliver rich contents like graphics and movies without any additional plugins like flash.
2. Better semantic support through new structural elements.
3. Cross platform support

Important features of HTML5
===========================
1. Graphics using <code> canvas </code> tag.
  <pre>
  eg; canvas id= "c" width="100" height="100">/canvas
  <script>
    var canvas = document.getElementById( "c" );
    var drawing_context = canvas.getContext( "2d" );
    drawing_context.fillStyle = "blue";
    drawing_context.fillRect( 50, 50, 100, 100 );
  </script>
  </pre>
  
 2. Media tags like audio and video
  <pre>
  eg; video width="640" height="360" controls
        source src="http://www.example.com/amazing_video.mp4"
      /video
  </pre>
      
 3. Extension to Javascript API like Geolocation, drag and drop, storage 
 4. Introduction to web workers
 5. New Structural Semantics
 <pre>
    nav
    article - self-contained composition that can logically be independently recreated outside of the page <br> 
              without losing it’s meaning. Individual blog posts or news stories
    section - flexible container for holding content that shares a common informational theme or purpose
    main
    header - introductory and navigational information about a section of the page
    footer - end of a section of content and contain additional information about the section. Author’s name,<br>
             copyright information,and related links
    aside - content that is only slightly related to the rest of the page.

Note: There can me many header and footer inside a page eg. header in article 1 and article 2
</pre>

6. New form control
<pre>
  calender
  date
  time
  url
  email
  search
 </pre>
 
Web workers
===========
Bring multi-threading in Javascript <br>
Script that runs in background(ie in another thread) without the page need to wait for it to complete <br>
User can continue to interact with the page when the web worker is running in the background <br>
Utilize thread like message to achieve parallelism <br>
Usually used for CPU intensive task <br>
 
Few Javascript object that are not accessible to HTML5 web workers are 
 - parent object
 - window object
 - document object
 
Types of web workers
1. Dedicated worker 
    - Accessible by the parent script that created it
    - Wide browser support
    - Simply tied to the main connection
2. Shared worker
    - Can be accessed from any script of same origin 
    - Limited browser support
    - Can work with multiple connection

Web worker works in the below steps
1. It should be executed on separate thread
2. Should be hosted in separate files from the main page
3. Worker object need to be instantiated to call them

Charset
=======
previous: meta charset="UTF-8" <br>
HTML5: meta http-equiv="Content-Type" content="text/html;charset=utf-8"

Difference between HTML specification and browser implementation
================================================================
Specification provides instruction on how a browser must interpret and render such a document <br>
A browser is said to “support” a specification if it handles valid documents according to the rules of the specification

Section inside article and article inside section example
========================================================
A personal dashboard page might contain a <code> section</code> for social network interactions as well as a <code>section</code> for the latest news articles, the latter of which could contain several <code>article</code> elements. <br>
An <code>article</code> might contain a <code>section</code> at the end for reader comments.

Difference between span and div
===============================
span : output with <code>display:inline</code> <br>
div : output with <code>display:block</code> <br>
span is used when we need our element to be displayed in a line one after another

Geolocation API
===============
Lets the user to share the physical location with chosen website <br>
Javascript captures lattitude and longitude and send the details to the backend server to process like showing the location in map <br>
Can be created as follows
<pre> var geolocation(service obj)= navigator.geolocation; </pre>

Difference between prop and attr
================================
Both are used to get and set values of a specified property of an element attribute

<pre>
attr() - returns default value of the property
prop() - returns the current value of the property
</pre>

Web Storage
===========
- Web pages can store data locally in the user browser
- More secure and faster than cookies
- Unlike cookies data is not included in every request, it is sent when asked for
- Data is stored in name value pair
- Web page can access the data stored by itself
- Storage limit is minimum 5MB greater than that of cookie(4KB)

Difference between local storage and session storage
====================================================
<strong> Local Storage </strong>
- Data stored is permanent
- Doesnot expires, remains in user computer until web page delete it or the user as browser to delete it.
- To Delete <code> localstorage.remove('key') or localstorage.clear() </code> need to be used
- Values stored in local storage can be accessed by all the windows and tabs from same origin
- Maximum size of local storage is 10-15 MB

<strong> Session Storage</strong>
- Same lifetime as top level window or browser tab in which the script that stored that is running
- When the window or tab is closed then the data is deleted
- Value stored is not shared. It will be visible to respective window or tab
- Maximum size is 5MB

Custom attribute
================
Starts with data- and get the value from JavaScript API or CSS
<pre>
div class="example" data-subject="physics" data-level="complex"
/div
</pre>

Datetime input ctrl Vs datetime-local input ctrl
=================================================
Both represent date and time (year,month,day,hour,minute,second,fraction of second) encoded according to ISO 8601

- Datetime - timezone set to UTC
- datatime-local - no timezone

Web Socket
=========
- Bi-directional for web application which operates over single socket
- Used to reduce the over-head of http
- When connection is established send data using send() and receive data using onMessage event handler
<code> var websocket = new WebSocket(url,[protocal]);</code>

Difference between HTML5 Application cache and browser cache
============================================================
- Application cache enables offline version of a web application
- Fetch few or all the application conent like HTML,CSS,JS locally
- Speeds up the site performance
- Not compulsary for the user to visit the web contents to be cached
- Done by
<pre>
html manifest="example.appcache"
/html
</pre>

Manifest file
=============
Basically a text file that dictates what need to be cached and what not when application cache is enabled

eg: <pre>
CACHE MANIFEST
CACHE
NETWORK
FALLBACK

CACHE MANIFEST
/decorate.css
/work.js
/amazing.jpg
</pre>

Lazy loading
============
- Design pattern commonly Used
- Loading code only when the user needs

Fieldset
=========
- Groups the related form elements
- It draws a box around the related elements
- It must start with <code> legend </code> tag to define the title
- Makes the form easier to understand

Server Sent Events
==================
Bi-directional communication channel prior to websocket
1. Event source interface: Allows client to recieve push notification from server as DOM events
2. Event stream: Data format to deliver individual updates

Web SQL Database
=================
- Used to manipulate client side DB
- Stores data in client side not server side

Ways to reduce page load time
==============================
- Reduce image size
- Remove unnecessary widgets
- Put CSS at top and script references at the bottom - Reduce look up , minimize redirection and caching

Optimize a website
==================
- Minimize http request
- Use Content Delivery Network
- Put style sheet at the top
- Put scripts at bottom
- Avoid css expression
- External JS and CSS
- Minify JS and CSS
- Avoid redirects
- Remove duplicate scripts
- Preload components
- Reduce number of DOM elements
- No 404
- Minimize DOM Access
- smart event handlers
- avoid filters
- optimize image
- Dont scale images in HTML

Difference between standard mode and quirks mode
================================================
Quirks mode 
- Default compactibility mode
- Vary from browser to browser
- Lack of consistency in appearance

Indexed DB
===========
- Used to store large amount of data in browser
- More efficient than webstorage
- Stores data as key value pair
- Asynchronous
- Non Relational

Micro Data
==========
- Used to nest the metadata within an existing content on the page
- Mechanism that allows machine readable data to be embed in the html in an easy to write manner



