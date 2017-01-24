## Repeated property names

Property names, specially within deep-nested objects, take a lot of function real-estate.

```
toggleFeedback: function() {
    // create the view if it does not exist
    if (!this.view.feedback) {
        this.view.feedback = new FeedbackView();
    }
    
    this.view.feedback.setData(this.model.toJSON());
    this.view.feedback.render();
    this.$el.append(this.view.feedback.el);
}

```

```
toggleFeedback: function() {
    this.view.feedback || (this.view.feedback = new FeedbackView()), this.view.feedback.setData(this.model.toJSON()), 
    this.view.feedback.render(), this.$el.append(this.view.feedback.el);
}
```
