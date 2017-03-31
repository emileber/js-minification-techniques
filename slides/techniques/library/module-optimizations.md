## Module scope

A common way to avoid polluting the global scope is to use [IIFE](https://en.wikipedia.org/wiki/Immediately-invoked_function_expression). Everything used twice or more should be stored into a local variable.


```
var MyLib = MyLib || {};
    
(function(_, Backbone, Component) {
    var _extend = _.extend, // function from library
    
        Model = Component.Model = Backbone.Model.extend({
            filterData: function(predicate, defaults){
                return _extend(defaults, _.filter(this.attributes, predicate));
            }
        }),
        View = Component.View = Backbone.View.extend({
            initialize: function(options) {
                this.options = _extend({ myDefault: "value" }, options);
                this.model = new Model();
            }
        });
    /* ... */
    return Component;
    
})(
    // inject dependencies
    _, Backbone, 
    MyLib.Component || (MyLib.Component = {})
);
```

