# 面试题汇总

---
##### 1. 用正则表达式匹配字符串，以字母开头，后面是数字、字符串或者下划线，长度为9-20

<details><summary><b>答案</b></summary>
<p>

``` javascript
var re=new RegExp("^[a-zA-Z]\w{9,20}$");
```

</p>
</details>

---
