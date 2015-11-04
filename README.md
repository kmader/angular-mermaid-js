angular-mermaid-js
==================

A working example of how to integrate the graph layout tool [mermaid](https://github.com/knsv/mermaid) with Angular.js. The important areas to consider are

1) Usage of sanitize on the mermaid object before rendering it on the page


	var gs = "graph TD; " + $scope.graphScript
	return $sce.trustAsHtml(gs);


2) Reinitializing the mermaid engine after updating the graph


	// Clear flag "this graph is initialized"
	angular.forEach(document.getElementsByClassName('mermaid'), function(elem) {
		elem.removeAttribute('data-processed');
	});
	
	// Graph reinicialization
	setTimeout(function(){mermaid.init();},1000)

## Live Demo
The index.html is the code for the live demo which can be seen here:
http://kmader.github.io/angular-mermaid-js/
