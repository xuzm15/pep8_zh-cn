# 代码布局
## 缩进

每个缩进登记使用4个空格。

连续的行需要将包裹的元素按列对其无论是使用Python在圆括号、方括号和大括号中隐式连接的行还是悬挂缩进[^1]。当使用悬挂缩进时，以下几点需要考虑；第一行不应该有任何参数，并且需要进一步的缩进来清晰地表示它是一个连续的行。

正确
```python
# 与左边括号对齐
foo = long_function_name(var_one, var_two,
                         var_three, var_four)

# 需要更多的缩进从而将它和其余部分分清
def long_function_name(
        var_one, var_two, var_three,
        var_four):
    print(var_one)

# 悬挂缩进需要增加等级
foo = long_function_name(
    var_one, var_two,
    var_three, var_four)
```

错误
```python
# 当未使用垂直对齐时，第一行不能有任何参数
foo = long_function_name(var_one, var_two,
    var_three, var_four)

# 当不能区分时，需要进一步地添加缩进
def long_function_name(
    var_one, var_two, var_three,
    var_four):
    print(var_one)
```

4空格规则对于连续行是可选的。

可选的
```python
# 悬挂缩进可以不是4个空格
foo = long_function_name(
  var_one, var_two,
  var_three, var_four)
```

当判断语句的if部分足够长以至于需要写多行时，值得关注到的是一个双字符的关键字（即if）加上一个空格，再加一个左圆括号的组合产生了一个天然的4空格缩进，因此会对多行条件中的接下来几行造成与if语句嵌套的部分产生视觉上的冲突。这篇PEP并没有明确地指出如何更好的在视觉上区分条件行和嵌套部分的方式。在这种情形下可以采取的方式包括，但不限于以下几点：
```python
# 没有多余的缩进
if (this_is_one_thing and
    that_is_another_thing):
    do_something()

# 加一个注释，它会为那些支持语
# 法高亮的编辑器提供一些区分度
if (this_is_one_thing and
    that_is_another_thing):
    # Since both conditions are true, we can frobnicate.
    do_something()

# 在条件行添加一些其他的缩进
if (this_is_one_thing
        and that_is_another_thing):
    do_something()
```

多行结构中的右括号可以放在列表的最后一行的第一个非空白字符的下边，像：
```python
my_list = [
    1, 2, 3,
    4, 5, 6,
    ]
result = some_function_that_takes_arguments(
    'a', 'b', 'c',
    'd', 'e', 'f',
    )
```

或者它可以放在开启多行结构的那行的第一个元素那里，像：
```python
my_list = [
    1, 2, 3,
    4, 5, 6,
]
result = some_function_that_takes_arguments(
    'a', 'b', 'c',
    'd', 'e', 'f',
)
```

## tab还是空格？

空格是更为推荐的缩进方式。

tab只适用于为了与已经使用tab作为缩进的编码保持一致的场景。

Python 3不允许tab和空格的混用。

Python 2中混用tab和空格的代码应当转化成仅适用空格的方式。

当采用Python 2命令的-t选项，它会报告非法混合使用tab和空格的警告，当使用-tt选项，这些警告变为错误。这些选项是强烈建议使用的。

## 最大行长度

将所有行限制在79个字符的宽度。

对于有更少结构限制的文本块（比如docstring或注释），每行的长度需要限制在72个字符。

限制编辑器窗口的宽度可以用于同时多个文件并排打开的情形，并且对于那些使用将两个版本在相邻行展示的代码查看工具有很好的使用效果。
























