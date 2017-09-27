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




