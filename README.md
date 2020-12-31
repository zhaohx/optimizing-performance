# optimizing-performance
Optimizing Performance of Web Application
## Ways to optimize
  * CSS,Javascript,DOM
  * Automation tools
  * Cache
  * PWA
***

### CSS,Javascript,DOM
  #### CSS
  * [CSS sprites](https://spritegen.website-performance.org)   
  * [SVG sprites](https://w3bits.com/svg-sprites/)
  * [IconFont](https://www.icofont.com/)
  * Base64 (Be careful to use it, it can reduce one http request but also increase HTML size and can not be cached)
  
  #### Javascript
  * Scripts  
  ```
  // bad example
  <head>
    <meta content="text/html; charset=utf-8" http-equiv="Content-Type">
    <meta name="viewport"
          content="width=device-width, initial-scale=1.0, user-scalable=0, minimum-scale=1.0, maximum-scale=1.0">
    <meta name="apple-mobile-web-app-title" content="">
    <meta name="apple-mobile-web-app-status-bar-style" content="black">
    <meta name="format-detection" content="telephone=no"/>
    <title>test</title>
    <script src="file1.js"></script>
    <script src="file2.js"></script>
    <script src="file3.js"></script>
  </head>
  ```
  ```
  // good example
  <head>
    <meta content="text/html; charset=utf-8" http-equiv="Content-Type">
    <meta name="viewport"
          content="width=device-width, initial-scale=1.0, user-scalable=0, minimum-scale=1.0, maximum-scale=1.0">
    <meta name="apple-mobile-web-app-title" content="">
    <meta name="apple-mobile-web-app-status-bar-style" content="black">
    <meta name="format-detection" content="telephone=no"/>
    <title>test</title>
  </head>
  <body>
    <div>Hello world</div>
    <script src="file1.js"></script>
    <script src="file2.js"></script>
    <script src="file3.js"></script>
  </body>
  ```
  
  * Get & Set
    - Local variable is faster than Global variable
    - More deep in the prototype, more slow to get
    ```
    // bad example
    window.location.href
    
    // good example
    location.href
    ```
    
  * Loops
    
  * String & RegExp
  
