# Optimizing Performance
Optimizing Performance of Web Application
## Ways to optimize
  * CSS,Javascript,DOM
  * Automation tools
  * Cache
  * Memory
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
   - Aviod to use for in
   - Be aware of the error "Maximum call stack size exceeded" when using recursion.Use iteration to avoid.
   ```
   // bad example
   let items = [1,2,3,4,5,6,7,8];
   for (let i = 0; i < items.length; i++) {
        //TODO: process(items[i])
   }
   
   // good example
   let items = [1,2,3,4,5,6,7,8];
   let length = items.length;
   for (let i = 0; i < length; i++) {
        //TODO: process(items[i])
   }
   ```
    
  * String & RegExp
   - Use + += to connect string rather than Array.join or Array.concat
   
   #### DOM
   * Get & Set
     - Use local variable to store a node
     - Use querySelectorAll
    
   * Reflow & Repaint
     - Use cache and reduce the number of changing the layout

***

### Automation tools
 #### webpack 
  - [SplitChunksPlugin](https://www.webpackjs.com/plugins/split-chunks-plugin/)
  - [Tree Shaking](https://webpack.js.org/guides/tree-shaking/)
  - [syntax-dynamic-import](https://webpack.wuhaolin.cn/4%E4%BC%98%E5%8C%96/4-12%E6%8C%89%E9%9C%80%E5%8A%A0%E8%BD%BD.html)
  - UglifyJS
  - DllPlugin: provide means to split bundles in a way that can drastically improve build time performance
  - [Scope Hoisting](https://webpack.wuhaolin.cn/4%E4%BC%98%E5%8C%96/4-14%E5%BC%80%E5%90%AFScopeHoisting.html)
  - [PrePack](https://prepack.io/) A tool that optimizes JavaScript source code: Computations that can be done at compile-time instead of run-time get eliminated
  - [HappyPack](https://github.com/amireh/happypack) makes initial webpack builds faster by transforming files
 ***
 
 ### Cache
 #### Browser cache
  - HTML meta
  - HTML5 appcache(Deprecated)
  - PWA
    - [Service worker](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API)
    - Web App Manifest
    - Push & Notifications
    - Add to Home Screen
 #### HTTP Cache
  - nginx 
  - CDN(Content Delivery Network)
  - HTTP2
 ***
 
 ### Memory
  - Closure
  - Timer
  - Event
  - Virtual list
