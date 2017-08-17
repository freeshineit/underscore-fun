简介：

*each* `_.each(obj, iteratee, [context])` Alias: * forEach *
遍历obj中的所有元素，按顺序用遍历输出每个元素。如果传递了context参数，则把iteratee绑定到context对象上。每次调用iteratee都会传递三个参数：`(element, index, obj)`。如果obj是个JavaScript对象，iteratee的参数是 `(value, key, obj))`。返回obj以方便链式调用。（愚人码头注：如果存在原生的forEach方法，Underscore就使用它代替。）

from：[@愚人码头](http://www.css88.com/doc/underscore1.8.2/)

(略有修改)

源码：

```js
    // The cornerstone, an `each` implementation, aka `forEach`.
    // Handles raw objects in addition to array-likes. Treats all
    // sparse array-likes as if they were dense.
    _.each = _.forEach = function(obj, iteratee, context) {
      iteratee = optimizeCb(iteratee, context);
      var i, length;
      if (isArrayLike(obj)) {
        for (i = 0, length = obj.length; i < length; i++) {
          iteratee(obj[i], i, obj);
        }
      } else {
        var keys = _.keys(obj);
        for (i = 0, length = keys.length; i < length; i++) {
          iteratee(obj[keys[i]], keys[i], obj);
        }
      }
      return obj;
    };

```


使用：

```js

(function(){
    _.each([99, 2, 3], (i) => {
        console.log(i);
    });

    _.forEach(['a','b','c','d'],(i) => {
        console.log(i);
    })






})()

```

result:

![each](./each.png)
