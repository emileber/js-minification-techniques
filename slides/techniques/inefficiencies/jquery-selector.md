## Inefficient jQuery

Another thing that is commonly repeated (and overly inefficient) is jQuery selectors.

```
$('#my-div').toggleClass('lol');
$('#my-div').append("<article>So HTML5</article>");
```

Each time `$('#my-div')`, jQuery traverses the DOM tree to find `<div id="my-div">`.
