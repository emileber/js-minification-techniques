## Useless verbosity

JavaScript lets you write what you want without complaining and won't suggest improvements.

So you might come across:

```
object["property"] = /*...*/

{ "property": /*...*/ }

a = (b * c);

x = a || (b && c);

function(options){
    /*...*/
    if (options !== undefined && options.something) {
        return true;
    } else {
        return false;
    }
}

```
