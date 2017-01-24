# Avoid `eval`

```
eval("var myObject = { value: " + calculatedValue + "};");
```

There are _almost_ no reason to use `eval`. 

If you think you know what you're doing and `eval` is the solution, think again.