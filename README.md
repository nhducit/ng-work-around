# ng-work-around
angular workaround for errors.

## angular interpolation do not work with IE.

- workaround: add `ng-attr-` prefix before html attribute.

    [ngAttr attribute bindings](https://docs.angularjs.org/guide/directive)
    
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
   
   [working plunker](http://plnkr.co/edit/TgxXfEX0mewfWAIczXnv?p=preview)