# 代码布局
## 缩进

每个缩进登记使用4个空格。

连续的行需要将包裹的元素按列对其无论是使用Python在圆括号、方括号和大括号中隐式连接的行还是悬挂缩进[^1]。当使用悬挂缩进时，以下几点需要考虑；第一行不应该有任何参数，并且需要进一步的缩进来清晰地表示它是一个连续的行。

正确
```python
# 与开的分隔符对齐
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

4空格规则对于连续行是可选的。

可选的
```python
# 悬挂缩进可以不是4个空格
foo = long_function_name(
  var_one, var_two,
  var_three, var_four)


























