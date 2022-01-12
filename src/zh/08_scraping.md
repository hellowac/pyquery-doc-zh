# 爬取

[requests]: http://docs.python-requests.org/en/latest/

`PyQuery` 能够从 `url` 加载 `html` 文档：

```python
>>> pq(your_url)
[<html>]
```

默认使用`python`的`urllib`包

如果安装了 **[requests]** ，那么它将使用它。 这允许您使用大多数 **[requests]** 参数：

```python
>>> pq(your_url, headers={'user-agent': 'pyquery'})
[<html>]

>>> pq(your_url, {'q': 'foo'}, method='post', verify=True)
[<html>]
```

## 超时

默认超时为 60 秒，您可以通过设置转发到底层 `urllib` 或 **[requests]** 库的超时参数来更改它。

## 会话

使用 **[requests]** 库时，您可以实例化一个在 `http` 调用之间保持状态的 **Session** 对象（例如 - 保持 `cookie` ）。 您可以设置会话参数以使用此会话对象。
