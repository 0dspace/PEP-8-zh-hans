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

#### <a id="references" href="#-references">参考</a>

| <a id="id8" href="#id1">[1]</a> | [PEP 7](https://www.python.org/dev/peps/pep-0007), C语言代码风格指南, van Rossum |
| ------------------------------- | ------------------------------------------------------------ |
| <a href="#id2" id="id9">[2]</a> | Barry's GNU Mailman style guide <http://barry.warsaw.us/software/STYLEGUIDE.txt> |
|                                 |                                                              |
|                                 |                                                              |
|                                 |                                                              |
|                                 |                                                              |

