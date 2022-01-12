# 快速开始

您可以使用 PyQuery 类从`字符串`、`lxml 文档`、`文件`或 `url` 加载 **xml** 文档：

```python
>>> from pyquery import PyQuery as pq
>>> from lxml import etree
>>> import urllib
>>> d = pq("<html></html>")
>>> d = pq(etree.fromstring("<html></html>"))
>>> d = pq(url=your_url)
>>> d = pq(url=your_url,
...        opener=lambda url, **kw: urlopen(url).read())
>>> d = pq(filename=path_to_html_file)
```

现在 `d` 就像 `jquery` 中的 `$` ：

```python
>>> d("#hello")
[<p#hello.hello>]
>>> p = d("#hello")
>>> print(p.html())
Hello world !
>>> p.html("you know <a href='http://python.org/'>Python</a> rocks")
[<p#hello.hello>]
>>> print(p.html())
you know <a href="http://python.org/">Python</a> rocks
>>> print(p.text())
you know Python rocks
```

您可以使用一些在 jQuery 中可用但在 css 中不标准的伪类，例如 `:first` `:last` `:even` `:odd` `:eq` `:lt` `:gt` `:checked` `:selected` `:file`:

```python
>>> d('p:first')
[<p#hello.hello>]
```
