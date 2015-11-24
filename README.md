# ng-work-around
angular workaround for errors

- angular interporlation do not work with IE.

- workaround: add `ng-attr-` prefix before html attribute.
    
    example:
     
    ```js
    ...
    $scope.awesomeId = 'awesome';
    ...
    ```
    
    ```html
    <div id="{{awesomeId}}"></div>
    ```
    
    to
    
    ```html
    <div ng-attr-id="{{awesomeId}}"></div>
    ```
    
    compile to:
    
    ```html
    <div ng-attr-id="{{awesomeId}}" id="awesome"></div>
    ```
    

    ```html
    <!doctype html>
    <html ng-app="plunker" >
    <head>
      <meta charset="utf-8">
      <title>AngularJS Plunker</title>
      <script>document.write('<base href="' + document.location + '" />');</script>
      <link rel="stylesheet" href="style.css">
      <script src="http://code.angularjs.org/1.1.3/angular.js"></script>
      <script src="app.js"></script>
    </head>
    <body ng-controller="MainCtrl" ng-init="backgroundColor='red'">
      <input ng-model="backgroundColor">
      <h1 style="background-color: {{backgroundColor}}">Works in Chrome, not IE</h1>
      <h1 ng-style="{'background-color': backgroundColor}">Works in All</h1>
    </body>
    </html>
    ```