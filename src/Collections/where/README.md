简介：

*where* `_.where(obj, attrs) `
遍历obj数组中的每一个值，返回一个数组，这个数组包含attrs中的属性的所有的键/值对。

源码：

```js

// Convenience version of a common use case of `filter`: selecting only objects
// containing specific `key:value` pairs.
_.where = function(obj, attrs) {
  return _.filter(obj, _.matcher(attrs));
};

```

使用：

```js
(function(){

    console.log(_.where([{'苹果':'🍎'},{'橘子':'🍊'},{'栗子':'🌰'}],{'香蕉':'🍌'}));
    console.log(_.where([{'苹果':'🍎'},{'橘子':'🍊'},{'香蕉':'🍌'},{'香蕉':'🍌','栗子':'🌰'}],{'香蕉':'🍌'}));

})()

```

result:

![where](./where.png)

方法分析：

[_.filter](../filter)

[_.matcher(attrs)](../../Objects/matcher)
