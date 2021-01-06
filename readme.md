# 面试题汇总

---
##### 1. 用正则表达式匹配字符串，以字母开头，后面是数字、字母、中文或者下划线，总长度为9-20

<details><summary><b>答案</b></summary>
<p>

``` regexp
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

console.log(str1.myTrim())
```

解释：

\s 匹配任何空白字符。(空格, 制表符, 换行符)
| 多选表现起来像 逻辑与。匹配|前面的或后面的表达式。
它可以用在分组里面，或在整个表达式中使用。会按顺序尝试匹配。

如果开头与结尾的内容不想匹配其他字符可以用|管道符代替

示例

```regexp
b(a|e|i)d
bad bud bod bed bid
```

</p>
</details>

---
