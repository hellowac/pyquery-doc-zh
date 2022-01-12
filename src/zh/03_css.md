# css

你可以使用css类：

```python
>>> p.addClass("toto")
[<p#hello.hello.toto>]
>>> p.toggleClass("titi toto")
[<p#hello.hello.titi>]
>>> p.removeClass("titi")
[<p#hello.hello>]
```

或 css 样式：

```python
>>> p.css("font-size", "15px")
[<p#hello.hello>]
>>> p.attr("style")
'font-size: 15px'
>>> p.css({"font-size": "17px"})
[<p#hello.hello>]
>>> p.attr("style")
'font-size: 17px'
```

与 **pythonic** 方式相同（ **'_'** 字符被翻译成 **'-'** ）：

```python
>>> p.css.font_size = "16px"
>>> p.attr.style
'font-size: 16px'
>>> p.css['font-size'] = "15px"
>>> p.attr.style
'font-size: 15px'
>>> p.css(font_size="16px")
[<p#hello.hello>]
>>> p.attr.style
'font-size: 16px'
>>> p.css = {"font-size": "17px"}
>>> p.attr.style
'font-size: 17px'
```
