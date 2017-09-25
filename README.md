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
    article - self-contained composition that can logically be independently recreated outside of the page without losing it’s                         meaning. Individual blog posts or news stories
    section - flexible container for holding content that shares a common informational theme or purpose
    main
    header - introductory and navigational information about a section of the page
    footer - end of a section of content and contain additional information about the section. Author’s name, copyright information,                  and related links
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
Bring multi-threading in Javascript
Script that runs in background(ie in another thread) without the page need to wait for it to complete
User can continue to interact with the page when the web worker is running in the background
Utilize thread like message to achieve parallelism
Usually used for CPU intensive task
 
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
  
