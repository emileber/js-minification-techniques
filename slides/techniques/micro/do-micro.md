## Micro optimizations

Do these easy micro optimizations instead.


```
object.property = /*...*/

{ property: /*...*/ }

a = b * c;

x = a || b && c; // && precedence already greater than ||

function(options) {
    options = options || {};
    /*...*/
    return options.something; // if you don't care about returning the raw value
    // if you want to strictly return a boolean
    // return Boolean(options.something);
}

```