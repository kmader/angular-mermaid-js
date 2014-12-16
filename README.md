angular-mermaid-js
==================

A working example of how to integrate the graph layout tool [mermaid](https://github.com/knsv/mermaid) with Angular.js. The important areas to consider are

1. Usage of sanitize on the mermaid object before rendering it on the page
```
var gs = "graph TD; " + $scope.graphScript
return $sce.trustAsHtml(gs);
```
2. Reinitializing the mermaid engine after updating the graph
```
setTimeout(function(){mermaid.init();},1000)
```
