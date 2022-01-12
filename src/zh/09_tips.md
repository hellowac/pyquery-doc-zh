# tips

## 转化为绝对链接

您可以将链接设为绝对链接，这对于页面抓取很有用：

```python
>>> d = pq(url=your_url, parser='html')
>>> d('form').attr('action')
'/form-submit'
>>> d.make_links_absolute()
[<html>]
```

## 使用不一样的解析器

默认情况下，`pyquery` 使用 `lxml` 包的 `xml` 解析器，如果它不起作用，则继续尝试来自 `lxml.html` 的 `html` 解析器。 `xml` 解析器在解析 `xhtml` 页面时有时会出现问题，因为解析器不会引发错误，而是会给出一个不可用的树（示例在 w3c.org 上）。

您还可以选择显式使用哪个解析器：

```python
>>> pq('<html><body><p>toto</p></body></html>', parser='xml')
[<html>]
>>> pq('<html><body><p>toto</p></body></html>', parser='html')
[<html>]
>>> pq('<html><body><p>toto</p></body></html>', parser='html_fragments')
[<p>]
```
