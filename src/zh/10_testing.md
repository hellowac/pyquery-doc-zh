# 测试

如果您想运行上面可以看到的测试，您应该执行以下操作：

```bash
>$ git clone git://github.com/gawel/pyquery.git
>$ cd pyquery
>$ python bootstrap.py
>$ bin/buildout install tox
>$ bin/tox
```

您可以通过执行以下操作来构建 `Sphinx` 文档：

```bash
>$ cd docs
>$ make html
```
