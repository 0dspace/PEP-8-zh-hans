# PEP 8 --- Python代码的风格指南
*ps:自己斗胆翻译PEP 8，主要是为了了解其规范并且提高自己的英语读写能力。*

来源：[PEP 8 -- Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/)

| PEP:                     | 8                                                            |
| ------------------------ | ------------------------------------------------------------ |
| **标题：**               | **Python代码的风格指南**                                     |
| **作者：**               | **Guido van Rossum <guido at python.org>, Barry Warsaw <barry at python.org>, Nick Coghlan <ncoghlan at gmail.com>**(人名不做翻译) |
| **状态：**               | **活跃**                                                     |
| **类型：**               | **Process**(不知道翻译成什么合适)                            |
| **创建时间：**           | **2001-07-05**                                               |
| **至今为止的发布时间：** | **2001-07-05**，**2013-08-01**                               |
| **历史：**               |                                                              |

### 目录：

* <a href="#introduction" id="-introduction">引言</a>
* <a href="#foolish" id="-foolish">愚蠢的一致性是小心行事的灾难</a>
* <a href="#code-lay-out" id="-code-lay-out">代码布局</a>
  * <a href="#indentation" id="-indentation">缩进</a>
* <a href="#references" id="-references">参考</a>


#### <a href="#-introduction" id="introduction">引言</a>

这篇文档给出了Python代码的编码约定，其中包括Python的主干发布版中的标准库。请参阅Python的C语言实现版中关于C语言代码风格之南 PEP 描述的配套信息<a id="id1" href="#id8">[1]</a>。

本文档和[PEP 257](https://www.python.org/dev/peps/pep-0257)（Docstring公约）改编自Guido最初的Python风格指南文章，并增加了一些Barry的风格指南<a href="#id9" id ="id2">[2]</a>。

随着时间的推移，这种风格会因为附加公约被修改而演变，并且过去的公约也会因为语言本身的改变而废除。

许多项目都有他们自己的编码风格指南。在发生任何冲突事件时，对于这个项目来说其特定项目的指南具有优先权。

#### <a href="#-foolish" id="foolish">愚蠢的一致性是小心行事的灾难</a>

Guido的主要见解之一是代码阅读的次数比编写次数多得多。这里提供的准则旨在提高代码的可读性并使其在各种Python代码中保持一致。如[PEP 20](https://www.python.org/dev/peps/pep-0020)所述，“可读性计数”。

风格指南是关于一致性的。 与此风格指南保持一致非常重要。 项目中的一致性更重要。一个模块或功能内的一致性是最重要的。

但是，知道什么时候不一致 —— 有时此”风格指南建议“并不适用。如有疑问，请使用您最佳的判断。 看看其他例子，并决定什么看起来最好。并且毫不犹豫的去请教！

值得一提的是：不要为了符合这个PEP规范而打破向后兼容性！

其他一些忽略某些特殊指南的合适的理由：

1. 在应用指南时，即使对于习惯阅读遵循此PEP代码的人来说，代码的可读性也会降低的时候。
2. 为了与周围的代码保持一致（也许是出于历史原因） —— 尽管这也是一个清理别人乱七八糟（真正的XP风格）的机会。
3. 因为相关代码早于此风格指南，而且没有其他理由要修改该代码。
4. 当代码需要与不支持此风格指南推荐的功能的旧版本的Python兼容时。

#### <a href="#-code-lay-out" id="code-lay-out">代码布局</a>

##### <a href="#-indentation" id="indentation">缩进</a>

每个缩进级别使用4个空格。

连续行应使用Python的隐式行连接括号，方括号和花括号，或使用悬挂缩进来垂直对齐包装元素。当使用悬挂式缩进的时候应该考虑以下因素：第一行不应该有参数，其余的行应该明确的将自己区分为连续的行。

推荐的格式：

```Python
# 与开始分隔符对齐
foo = long_function_name(var_one, var_two,
                         var_three, var_four)

# 在内部使用更多的缩进来区分参数和其余代码
def long_function_name(
		var_one, var_two, var_three,
		var_four):
    print(var_one)

# 悬挂式缩进应该提高一个级别
foo = long_function_name(
	var_one, var_two,
	var_three, var_four)
```

不推荐的格式：

```Python
# 当不使用垂直对齐的时候严禁参数在第一行
foo = long_function_name(var_one, var_two,
	var_three, var_four)

# 当缩进不可区分的时候需要使用更多的缩进
def long_function_name(
	var_one, var_two, var_three,
	var_four):
    print(var_one)
```

对于连续的行来说"4空格规则"是可选的。

可选的格式：

```Python
# 悬挂式缩进可以不使用4个空格
foo = long_function_name(
  var_one, var_two,
  var_three, var_four)
```

当一个if语句的条件部分长到需要写成多行的时候，通过合并两个字符的关键字加一个单个空格再加一个左括号而为多行条件的连续行创建一个自然的4空格缩进是毫无用处的。这会与在if语句内部本就该进行4空格缩进的代码产生一个视觉的冲突。这个 PEP 没有明确的说明如何(或是否)对这种if语句内部的多行条件进行进一步的视觉区分。这种情况下的可接受的选项包括但不限于：

```Python
# 没有额外的缩进
if (this_is_one_thing and
    that_is_another_thing):
    do_something()

# 添加一条注释，这将在编辑器中提供一些区分
# 支持语法高亮
if (this_is_one_thing and
    that_is_another_thing):
    # 当两个条件都是 真 的时候继续
    do_something()

# 在条件的下一行添加额外的缩进
if (this_is_one_thing
   		and that_is_another_thing):
    do_something()
```

（另请参阅下面关于是否在二元运算符之前或之后中断的讨论。）

多行结构中的右括弧/方括号/花括号可以也放在列表的最后一行的第一个非空白字符下，如下所示：

```Python
my_list = [
    1, 2, 3,
    4, 5, 6,
	]
result = some_function_that_takes_arguments(
	'a', 'b', 'c',
	'd', 'e', 'f',
	)
```

或者放在开始这个多行结构的第一个字符下，如下所示：

```Python
my_list = [
    1, 2, 3,
    4, 5, 6,
]
result = some_function_that_takes_arguments(
	'a', 'b', 'c',
	'd', 'e', 'f',
)
```



#### <a id="references" href="#-references">参考</a>

| <a id="id8" href="#id1">[1]</a> | [PEP 7](https://www.python.org/dev/peps/pep-0007), C语言代码风格指南, van Rossum |
| ------------------------------- | ------------------------------------------------------------ |
| <a href="#id2" id="id9">[2]</a> | Barry's GNU Mailman style guide <http://barry.warsaw.us/software/STYLEGUIDE.txt> |
|                                 |                                                              |
|                                 |                                                              |
|                                 |                                                              |
|                                 |                                                              |

