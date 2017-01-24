## Module scope

When writing a library, you define and use a lot of shared objects and other library functions.


```
(function(_, Backbone) {
    var MyLib = {};
    MyLib.Component = {};
    
    MyLib.Component.Model = Backbone.Model.extend({
        filterData: function(predicate, defaults){
            return _.extend(defaults, _.filter(this.attributes, predicate));
        }
    });
    
    
    MyLib.Component.View = Backbone.View.extend({
        initialize: function(options) {
            this.options = _.extend({ myDefault: "value" }, options);
            this.model = new MyLib.Component.Model();
        }
    });
    /* ... */
    return MyLib;
    
})(_, Backbone);
```