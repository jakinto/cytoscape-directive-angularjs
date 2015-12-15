# cytoscape-directive-angularjs

An AngularJS directive for Cytoscape JS library

##How to run
```{r, engine='bash', count_lines}
git clone https://github.com/jakinto/cytoscape-directive-angularjs
bower install
python -m SimpleHTTPServer 8888
```
Open your browser on [http://localhost:8888/examples/basic.html](http://localhost:8888/examples/basic.html)

##Attributes
#####elements
List of nodes and egdes to start with. Any modification of this attribute will cause the recreation of the graph. This attribute is mandatory.
#####styles
Stylesheet for the graph. Any modification of this attribute will cause the recreation of the graph. This attribute is mandatory.
#####layout
Graph layout algorithm. Any modification of this attribute will cause the recreation of the graph. This attribute is mandatory.
#####selected-elements
List of current selected elements. You should $watch this attribute to work with it. This attribute is optional.
#####highlight-by-name
Attribute that contains the name of the elements to highlight. This attribute is optional.
#####on-complete
Function that is called when the graph creation finalizes. This attribute is optional.
#####on-change
Function that is called each time the graph changes its elements. This attribute is optional.
#####navigator-container-id
HTML element id of the graph navigator plugin (https://github.com/cytoscape/cytoscape.js-navigator). This attribute is optional.
#####context-menu-commands
Object that represents the commands of the context menu plugin (https://github.com/cytoscape/cytoscape.js-cxtmenu). This attribute is optional. This object looks like:

```{r, engine='bash', count_lines}
  [{
      content: 'Edit',
      disabled: true
  }, {
      content: 'Mark',
      disabled: true
  }, {
      content: 'Remove',
      disabled: true
  }, {
      content: 'Log date',
      select: function(element) {
          console.log(new Date());
      },
  }]
```
##Events
#####cytoscapeAddElements
Event you should broadcast if you want to add elements to the graph. 
* **elements:**Elements to add to graph
* **forceApply:**```true``` to execute ```$scope.$apply()``` at the end.

Example of use:
```{r, engine='bash', count_lines}
  $scope.$broadcast('cytoscapeAddElements', {
      elements: [{
          data: {
              id: '1',
              name: 'Node1'
          }
      }, {
          data: {
              id: '2',
              name: 'Node2'
          }
      }],
      forceApply: false
  });
```
#####cytoscapeDeleteElements
Event you should broadcast if you want to remove elements from the graph. 
* **elements:**Elements to remove from the graph
* **forceApply:**```true``` to execute ```$scope.$apply()``` at the end.

##Contributors
* [0xNacho](http://github.com/0xNacho)
