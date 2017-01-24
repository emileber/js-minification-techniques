## Module optimizations

Like mentionned before, everything used twice or more can be stored into a local variable.


```
(function(_, Backbone) {
    var _extend = _.extend, // function from library
        MyLib = {},
        Component = MyLib.Component = {}, // sub-module within our library
    
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
    return MyLib;
    
})(_, Backbone);
```