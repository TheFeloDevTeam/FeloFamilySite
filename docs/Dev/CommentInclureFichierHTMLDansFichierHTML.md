
There are some methods like Server Side Includes which allow us to include other HTML files into a web page on a webserver like
1
    
<!-- #include virtual="./common.html" -->

But this technique require server side setting and may be not supported by some web hosting.

Another way to include .html in a web page is using jQuery insertion.

### Create the index.html as follow.
    
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/1.7.2/jquery.min.js"></script>
    <script type="text/javascript" src="script.js"></script>
  </head>
  <body>
    <div id="header">
      <!-- Content will be inserted by jQuery from header.html -->
    </div>
    <div>body</div>
  </body>
</html>

 
### Create the header.html which will be inserted in the #header div above.

    
<header>
  <h1></h1>
  <nav>
    <ul>
      <li><a href="#">link 1</a></li>
      <li><a href="#">link 2</a></li>
      <li><a href="#">link 3</a></li>
    </ul>
  </nav>
</header>

 

### Create the script.js
    
$(document).ready(function(){ 
  $.get("header.html", function(data) {
    $("#header").html(data);
  });
}); 

## Références

https://eureka.ykyuen.info/2012/10/06/html-include-html-using-jquery/

