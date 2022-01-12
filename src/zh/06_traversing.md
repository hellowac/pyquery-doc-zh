# 连调

支持一些 jQuery 遍历方法。 这里有一些例子。

您可以使用字符串选择器过滤选择列表：

```python
>>> d = pq('<p id="hello" class="hello"><a/></p><p id="test"><a/></p>')
>>> d('p').filter('.hello')
[<p#hello.hello>]
```

可以使用 `eq` 选择单个元素：

```python
>>> d('p').eq(0)
[<p#hello.hello>]
```

您可以找到嵌套元素：

```python
>>> d('p').find('a')
[<a>, <a>]
>>> d('p').eq(1).find('a')
[<a>]
```

使用 `end` 也支持突破一个遍历级别：

```python
>>> d('p').find('a').end()
[<p#hello.hello>, <p#test>]
>>> d('p').eq(0).end()
[<p#hello.hello>, <p#test>]
>>> d('p').filter(lambda i: i == 1).end()
[<p#hello.hello>, <p#test>]
```

如果你想选择一个 **'.'** ，如果你需要转义 **'.'**：

```python
>>> d = pq('<p id="hello.you"><a/></p><p id="test"><a/></p>')
>>> d('#hello\.you')
[<p#hello.you>]
```
