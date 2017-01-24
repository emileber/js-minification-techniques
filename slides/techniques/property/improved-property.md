## Improved property names

Any property name used two or more times should be stored into a local variable.

```
toggleFeedback: function() {
    var view = this.view,
        // create the view if it does not exist
        feedback = view.feedback || (view.feedback = new FeedbackView());
        
    this.$el.append(
        feedback
            .setData(this.model.toJSON()) // chaining calls
            .render()
            .el
    );
}

```

```
toggleFeedback: function() {
    var e = this.view, t = e.feedback || (e.feedback = new FeedbackView());
    this.$el.append(t.setData(this.model.toJSON()).render().el);
}
```
