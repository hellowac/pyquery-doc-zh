# 控制内容

您还可以在标签末尾添加内容：

```python
>>> d = pq('<p class="hello" id="hello">you know Python rocks</p>')
>>> d('p').append(' check out <a href="http://reddit.com/r/python"><span>reddit</span></a>')
[<p#hello.hello>]
>>> print(d)
<p class="hello" id="hello">you know Python rocks check out <a href="http://reddit.com/r/python"><span>reddit</span></a></p>
```

或从头开始：

```python
>>> p = d('p')
>>> p.prepend('check out <a href="http://reddit.com/r/python">reddit</a>')
[<p#hello.hello>]
>>> print(p.html())
check out <a href="http://reddit.com/r/python">reddit</a>you know ...
```

将一个元素添加或附加到另一个元素中：

```python
>>> d = pq('<html><body><div id="test"><a href="http://python.org">python</a> !</div></body></html>')
p.prependTo(d('#test'))
[<p#hello.hello>]
print(d('#test').html())
<p class="hello" ...
```

在一个元素后面插入一个元素

```python
>>> p.insertAfter(d('#test'))
[<p#hello.hello>]
>>> print(d('#test').html())
<a href="http://python.org">python</a> !
```

或之前:

```python
>>> p.insertBefore(d('#test'))
[<p#hello.hello>]
>>> print(d('body').html())
<p class="hello" id="hello">...
```

为每个元素做某些事：

```python
>>> p.each(lambda i, e: pq(e).addClass('hello2'))
[<p#hello.hello.hello2>]
```

删除一个元素:

```python
>>> d = pq('<html><body><p id="id">Yeah!</p><p>python rocks !</p></div></html>')
>>> d.remove('p#id')
[<html>]
>>> d('p#id')
[]
```

清空元素内容

```python
>>> d('p').empty()
[<p>]

```

你可以取回修改后的html：

```python
>>> print(d)
<html><body><p/></body></html>
```

你可以生成 html ：

```python
>>> from pyquery import PyQuery as pq
>>> print(pq('<div>Yeah !</div>').addClass('myclass') + pq('<b>cool</b>'))
<div class="myclass">Yeah !</div><b>cool</b>
```

删除所有命名空间：

```python
>>> d = pq('<foo xmlns="http://example.com/foo"></foo>')
>>> d
[<{http://example.com/foo}foo>]
>>> d.remove_namespaces()
[<foo>]
```
