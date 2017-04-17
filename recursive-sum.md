# Ch. 3+4 Homework

__Create a recursive sum function.__

[Link to working jsfiddle example](https://jsfiddle.net/meshuggie/kzm7aku2/)

```javascript
"use strict";

(function() {
  var arr = [2,5,6,7];
  var test = {
    base: 0,
    sum: function() {
      if (arr.length == 0) {
        return this.base;
      } else {
        this.base = this.base + arr.shift();
        this.sum();
      }
      return this.base;
    },
    print: function(i, el) {
      var li = document.createElement('li');
      i = document.createTextNode(i);
      li.appendChild(i);
      document.getElementsByClassName(el)[0].appendChild(li);
    }
  }
  test.print(arr.toString(), 'input');
  var sum = test.sum(arr);
  test.print(sum, 'output');
})();
```
