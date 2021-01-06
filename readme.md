# 面试题汇总

##### 1. 用正则表达式匹配字符串，以字母开头，后面是数字、字母、中文或者下划线，总长度为9-20

<details><summary><b>答案</b></summary>
<p>

``` javascript
^[a-zA-Z][\u4e00-\u9fa5\w]{8,20}$
```

</p>
</details>

---
##### 2. js字符串两边截取空白的trim的原型方法的实现

<details><summary><b>答案</b></summary>
<p>

``` javascript
String.prototype.myTrim = function (){
    return this.replace(/^\s*|\s*$/,'')// /^\s.*\s*$/
}
let str1 = ' winson '

console.log(str1.myTrim()) // => 输出：winson
```

解释：

\s 匹配任何空白字符。(空格, 制表符, 换行符)
| 多选表现起来像 逻辑与。匹配|前面的或后面的表达式。
它可以用在分组里面，或在整个表达式中使用。会按顺序尝试匹配。

如果开头与结尾的内容不想匹配其他字符可以用|管道符代替

示例

``` javascript
b(a|e|i)d
bad bud bod bed bid
```

</p>
</details>

---
##### 3. css垂直居中方法

<details><summary><b>答案</b></summary>
<p>
在不清楚高度的情况下

1. flex布局
父元素

``` css
display:flex;
align-item:center
```

2. translateY+position

``` css
position:absloute;
top:50%;
transform:translateY(-50%);
或者
position:relative;
top:50%;
transform:translateY(-50%);
```

清楚高度的情况下

子元素的top = (父元素的高度 - 子元素的高度) / 2
</p>
</details>

---

##### 4. 写一个div+css布局，左边图片右边文字，文字环绕图片，外面容器固定宽度，文字不固定

<details><summary><b>答案</b></summary>
<p>
图片加float:left属性

遇到英文要加word-break:break-all
</p>
</details>

---

##### 5. 谈谈对repaint和reflow理解

<details><summary><b>答案</b></summary>
<p>

```
repaint(重绘):指的是一种不会影响当前DOM结构和布局的一种重绘动作。
reflow(回流):要发生在 DOM 树被操作的时候，任何改变 DOM 的结构和布局都会产生 Reflow。但一个元素的 Reflow 操作发生时，它的所有父元素和子元素都会放生 Reflow，最后 Reflow 必然会导致 Repaint 的产生。
严重性：
在性能优先的前提下，reflow的性能消耗要比repaint的大。
体现：
repaint是某个dom元素进行重绘，reflow是整个页面进行重排，也就是对页面所有的dom元素渲染。
如何触发reflow和repaint
repaint的触发：
不可见到可见（visibility 样式属性）;颜色或图片变化（background, border-color, color 样式属性）;text-align、a：hover也会造成重绘，伪类引起的颜色等变化不会导致页面的回流，仅仅会触发重绘。不改变页面元素大小，形状和位置，但改变其外观的变化
reflow的触发：浏览器窗口的变化;DOM 节点的添加删除操作一些改变页面元素大小，形状和位置的操作的触发。
如何尽量避免回流reflow：
a、尽可能在dom末稍通过修改class来修改元素的style属性，尽可能减少受影响的dom元素。
b、避免设置多项内联样式，使用常用的class方式进行设置样式，以避免设置样式时访问dom的低效率。
c、设置动画元素position属性为fixed或absolute：由于当前元素从dom流中独立出来，因此受影响的只有当前元素。
d、牺牲平滑度满足性能：动画精度太强，会造成更多的repaint/reflow，牺牲精度，能满足性能的损耗，获取性能和平滑度的平衡。
f、避免使用table进行布局，table每个元素的大小以及内容的改变，都会导致整个table进行重新计算，造成大幅度的repaint或者reflow。改用div则可以针对性的repaint和避免不必要的reflow。
g、避免在css中使用运算式
```

</p>
</details>

---
