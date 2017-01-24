##  Techniques

Mostly _abuse_ local identifier replacement

```
function test(myParam, other) {
    var test = myParam.getValue();
    if (test) return test + other;
}
```

```
function test(t,e){var n=t.getValue();return n?n+e:void 0}
```