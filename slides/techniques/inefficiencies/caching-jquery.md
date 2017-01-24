## Cache jQuery objects

Instead of querying the DOM repeatedly, cache the object.

```
var $myDiv = $('#my-div').toggleClass('lol');
/*...*/
$myDiv.append("<article>So HTML5</article>");
```