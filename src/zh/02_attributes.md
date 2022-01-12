# 属性

使用属性选择特定标签在属性选择器中，值应该是有效的 CSS 标识符或引用为字符串：

```python
>>> d = pq("<option value='1'><option value='2'>")
>>> d('option[value="1"]')
[<option>]
```

您可以使用 **jquery API** 使用属性：

```python
>>> p = pq('<p id="hello" class="hello"></p>')('p')
>>> p.attr("id")
'hello'
>>> p.attr("id", "plop")
[<p#plop.hello>]
>>> p.attr("id", "hello")
[<p#hello.hello>]
```

或者以更 **Pythonic** 的方式：

```python
>>> p.attr.id = "plop"
>>> p.attr.id
'plop'
>>> p.attr["id"] = "ola"
>>> p.attr["id"]
'ola'
>>> p.attr(id='hello', class_='hello2')
[<p#hello.hello2>]
>>> p.attr.class_
'hello2'
>>> p.attr.class_ = 'hello'
```
