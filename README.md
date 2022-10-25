# 使用Hightlight.js完成的代码格式化
经验总结：
想在网页中完美的呈现出原始代码所有格式（如html 的标签）可以如下：
1. 使用过时的 xmp 标签，结合pre 和 code:
```
<pre>
    <code>
        <xmp>
            ...代码
        </xmp>
    <code>
</pre>
```
2. 使用JavaScript 结合原始代码的文本，代码文本只能使用后台的数据库存储，或者textarea标签存储。如果在网页
中直接存储，会被浏览器进行修改（如：自动补齐标签），然后使用lodash.escap函数，将所有的特殊字符进行转义，如：> 变成 &gt; ,转义后的字符串，再提交给 code的innerHTML即可，如代码所示。