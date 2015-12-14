# cytoscape-directive-angularjs

An AngularJS directive for Cytoscape JS library

##How to run
```{r, engine='bash', count_lines}
git clone https://github.com/jakinto/cytoscape-directive-angularjs
bower install
python -m SimpleHTTPServer 8888
```
Open your browser on <a href="http://localhost:8888/examples/basic.html">http://localhost:8888/examples/basic.html</a>

##Attributes
####elements
List of nodes and egdes to start with. Any modification of this attribute will cause the recreation of the graph. This attribute is mandatory.
####styles
Stylesheet for the graph. Any modification of this attribute will cause the recreation of the graph. This attribute is mandatory.
####layout
Graph layout algorithm. Any modification of this attribute will cause the recreation of the graph. This attribute is mandatory.
####selected-elements
List of current selected elements. You should $watch this attribute to work with it. This attribute is optional.
####add-elements
Elements to add to the graph. This attribute is optional.
####delete-elements
Elements to remove from the graph. This attribute is optional.
####highlight-by-name
Name of the elements to highlight. This attribute is optional.
####on-complete
Function that is called when the graph creation finalizes. This attribute is optional.
####on-change
Function that is called each time the graph changes its elements. This attribute is optional.
####navigator-container-id
HTML element id of the graph navigator. This attribute is optional.

##Contributors
* [0xNacho](http://github.com/0xNacho)
