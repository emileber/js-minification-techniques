# Avoid `eval`

`eval` prevent any optimizations.

```
funtion evil(paramValue) {
    eval("var myObject = { value: " + paramValue + "};");
}
```

There are _almost_ no reason to use `eval`. 

If you think you know what you're doing and `eval` is the solution, **think again**.