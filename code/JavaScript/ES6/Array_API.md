# Array API

### Array.prototype.splite 方法

#### 记录一个用 splite() 来删除数组中某元素所产生的 bug

一般我们用 `[1, 2, 3, 4].splite(0, 1);` 来删除数组中的第一个元素。

但如果 splite 的第一个参数是一个传进来的变量，

那我们就要多考虑到一个情况，就是这个变量可能是 **undefined**。

因为 `[1, 2, 3, 4].splite(undefined, 1);` 还是会删掉第一个元素，
但很明显，如果是 undefined，那我们希望什么也不要被删掉。

所以如果有变量，那在传入 splite 之前要做判断，是 undefined 就不用 splite 了。

### 遍历数组的多种方式

1. map
2. foreach
3. for
4. filter
5. reduce

分别的使用场景：

1. `map`
   - 在拿到一个很大的数组，但我只需要其中一小部分数据时，可以用 map 将其取出来；
   - 需要将数组按照某种规则映射为另一个数组；
2. `forEach` / `for of`
   - 只需要进行简单的数组遍历；
3. `for of`
   - 需要对迭代器进行遍历时；
4. `filter`
   - 需要过滤出所有符合条件的项（返回的是由所有符合条件项所组成的数组）；
5. `map` 结合 `filter`
   - 先映射成新的数组，再从中过滤出符合条件的项。

> 千万不要因为过分追求性能，而忽略了语义和可读性。

参考资料：

- [为了性能选择for循环遍历？--掘金](https://juejin.cn/post/6844904191425511432)