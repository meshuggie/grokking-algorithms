# Ch. 3+4 Homework

__Create a sorting function using quicksort.__
_Uses divide-and-conquer method._

[Link to working jsfiddle example](https://jsfiddle.net/meshuggie/5p4vd5ha/)

```javascript
"use strict";

(function() {
  var numSet = [2,62,9,18,32,8,53];
  var test = {
    quicksort: function(arr) {
      if (arr.length < 2) {
        return arr;
      } else {
        var index = Math.round(arr.length / 2);
        var pivot = arr[index];
        var less = [];
        var greater = [];
        arr.forEach(function(x) {
          if (x < pivot) {
            less.push(x);
          } else if (x > pivot) {
            greater.push(x);
          }
        });
        return this.quicksort(less).concat(pivot, this.quicksort(greater));
      }
    },
    print: function(i, el) {
      var li = document.createElement('li');
      i = document.createTextNode(i);
      li.appendChild(i);
      document.getElementsByClassName(el)[0].appendChild(li);
    }
  }
  test.print(numSet.toString(), 'input');
  var sorted = test.quicksort(numSet);
  test.print(sorted, 'output');
})();
```
