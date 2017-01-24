## Don't fear more lines

Even if the original function has fewer lines doesn't mean it is better.

```
original: function(value){
    this.view.myView.model.set('test', value);
    return this.view.myView.model;
}
```

```
improved: function(value){
    var model = this.view.myView.model; // Oh no!! One more line!
    model.set('test', value);
    return model;
}
```

In the `improved` function, it's easier to see we're going to work on `myView`'s model.