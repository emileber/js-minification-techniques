## Polluting the global scope

If not properly scoped, all these shared identifier pollutes the global scope and it could cause collisions with someone else's globals.


```
var MyModel = Backbone.Model.extend({
    filterData: function(predicate, defaults){
        return _.extend(defaults, _.filter(this.attributes, predicate));
    }
});


var MyView = Backbone.View.extend({
    initialize: function(options) {
        this.options = _.extend({ myDefault: "value" }, options);
        this.model = new MyModel();
    }
});
// ...
```