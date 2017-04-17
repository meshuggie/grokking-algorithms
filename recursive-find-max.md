# Ch. 3+4 Homework

__Find the maximum number in a list.__

[Link to working jsfiddle example](https://jsfiddle.net/meshuggie/833h7owc/)

```javascript
"use strict";

(function() {
  var arr = [2,5,6,7];
  var test = {
    base: 0,
    max: function() {
      if (arr.length == 0) {
        return this.base;
      } else {
        var next = arr.shift();
        this.base = (this.base < next) ? next : this.base;
        this.max();
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
  var max = test.max(arr);
  test.print(max, 'output');
})();
```
