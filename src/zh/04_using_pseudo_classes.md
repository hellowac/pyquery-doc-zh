# 使用伪类

* **B**: [:button](#button)
* **C**: [:checkbox](#checkbox) 、 [:checked](#checked)、 [:child](#child)、 [:contains](#contains)
* **D**: [:descendant](#descendant)、[:disabled](#disabled)
* **E**: [:empty](#empty)、[:enabled](#enabled)、[:eq()](#eq)、[:even](#even)
* **F**: [:file](#file)、[:first](#first)
* **G**: [:gt()](#gt)
* **H**: [:has()](#has)、[:header](#header)、[:hidden](#hidden)
* **I**: [:image](#image)、[:input](#input)
* **L**: [:last](#last)、[:lt()](#lt)
* **O**: [:odd](#odd)
* **P**: [:parent](#parent)、[:password](#password)、[:pseudo](#pseudo)
* **R**: [:radio](#radio)、[:reset](#reset)
* **S**: [:selected](#selected)、[:submit](#submit)
* **T**: [:text](#text)

## :button

Matches all button input elements and the button element:

匹配所有 `type=button`类型的 `input`元素 和 `button` 元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery(('<div><input type="button"/>'
...      '<button></button></div>'))
>>> d(':button')
[<input>, <button>]
```

## :checkbox

Matches all checkbox input elements:

匹配所有复选框 `input` 元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><input type="checkbox"/></div>')
>>> d('input:checkbox')
[<input>]
```

## :checked

Matches all checked input elements:

匹配所有被选中的 `input` 元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><input checked="checked"/></div>')
>>> d('input:checked')
[<input>]
```

## :child

right is an immediate child of left

right 是 left 的直接孩子

## :contains

Matches all elements that contain the given text

匹配包含给定文本的所有元素

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><h1/><h1 class="title">title</h1></div>')
>>> d('h1:contains("title")')
[<h1.title>]
```

## :descendant

right is a child, grand-child or further descendant of left

`right` 是 `left` 的孩子、孙子或进一步的后代

## :disabled

Matches all elements that are disabled:

匹配所有被禁用的元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><input disabled="disabled"/></div>')
>>> d('input:disabled')
[<input>]
```

## :empty

Match all elements that do not contain other elements:

匹配所有不包含其他元素的元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><h1><span>title</span></h1><h2/></div>')
>>> d(':empty')
[<h2>]
```

## :enabled

Matches all elements that are enabled:

匹配所有启用的元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><input value="foo" /></div>')
>>> d('input:enabled')
[<input>]
```

## :eq()

Matches a single element by its index:

按索引匹配单个元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><h1 class="first"/><h1 class="last"/></div>')
>>> d('h1:eq(0)')
[<h1.first>]
>>> d('h1:eq(1)')
[<h1.last>]
```

## :even

Matches even elements, zero-indexed:

匹配偶数元素，零索引：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><p></p><p class="last"></p></div>')
>>> d('p:even')
[<p>]
```

## :file

Matches all input elements of type file:

匹配文件类型的所有`input`元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><input type="file"/></div>')
>>> d('input:file')
[<input>]
```

## :first

Matches the first selected element:

匹配第一个选定的元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><p class="first"></p><p></p></div>')
>>> d('p:first')
[<p.first>]
```

## :gt()

Matches all elements with an index over the given one:

匹配索引超过给定元素的所有元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><h1 class="first"/><h1 class="last"/></div>')
>>> d('h1:gt(0)')
[<h1.last>]
```

## :has()

Matches elements which contain at least one element that matches the specified selector. <https://api.jquery.com/has-selector/>

匹配至少包含一个与指定选择器匹配的元素的元素。参考: <https://api.jquery.com/has-selector/>

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div class="foo"><div class="bar"></div></div>')
>>> d('.foo:has(".baz")')
[]
>>> d('.foo:has(".foo")')
[]
>>> d('.foo:has(".bar")')
[<div.foo>]
>>> d('.foo:has(div)')
[<div.foo>]
```

## :header

Matches all header elelements (h1, …, h6):

匹配所有标题元素（h1，...，h6）：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><h1>title</h1></div>')
>>> d(':header')
[<h1>]
```

### :hidden

Matches all hidden input elements:

匹配所有隐藏的`input`元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><input type="hidden"/></div>')
>>> d('input:hidden')
[<input>]
```

## :image

Matches all image input elements:

匹配所有 `type=image` 的 `input` 元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><input type="image"/></div>')
>>> d('input:image')
[<input>]
```

## :input

Matches all input elements:

匹配所有`input`元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery(('<div><input type="file"/>'
...         '<textarea></textarea></div>'))
>>> d(':input')
[<input>, <textarea>]
```

## :last

Matches the last selected element:

匹配最后选择的元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><p></p><p class="last"></p></div>')
>>> d('p:last')
[<p.last>]
```

## :lt()

Matches all elements with an index below the given one:

匹配索引低于给定索引的所有元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><h1 class="first"/><h1 class="last"/></div>')
>>> d('h1:lt(1)')
[<h1.first>]
```

## :odd

Matches odd elements, zero-indexed:

匹配奇数元素，零索引：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><p></p><p class="last"></p></div>')
>>> d('p:odd')
[<p.last>]
```

## :parent

Match all elements that contain other elements:

匹配所有包含其他元素的元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><h1><span>title</span></h1><h1/></div>')
>>> d('h1:parent')
[<h1>]
```

## :password

Matches all password input elements:

匹配所有密码输入元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><input type="password"/></div>')
>>> d('input:password')
[<input>]
```

## :pseudo

Translate a pseudo-element.

翻译一个伪元素。

> Defaults to not supporting pseudo-elements at all, but can be overridden by sub-classes
>
> 默认根本不支持伪元素，但可以被子类覆盖

## :radio

Matches all radio input elements:

匹配所有单选输入元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><input type="radio"/></div>')
>>> d('input:radio')
[<input>]
```

## reset

Matches all reset input elements:

匹配所有复位输入元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><input type="reset"/></div>')
>>> d('input:reset')
[<input>]
```

## selected

Matches all elements that are selected:

匹配所有被选中的元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<select><option selected="selected"/></select>')
>>> d('option:selected')
[<option>]
```

## submit

Matches all submit input elements:

匹配所有提交输入元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><input type="submit"/></div>')
>>> d('input:submit')
[<input>]
```

## text

Matches all text input elements:

匹配所有文本输入元素：

```python
>>> from pyquery import PyQuery
>>> d = PyQuery('<div><input type="text"/></div>')
>>> d('input:text')
[<input>]
```
