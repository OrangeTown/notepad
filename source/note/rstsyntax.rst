==============================
reStructuredText(reST)语法示例
==============================

详细的用法可以参考:

* `reStructuredText Primer <http://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html>`_
* `Quick reStructuredText <http://docutils.sourceforge.net/docs/user/rst/quickref.html>`_
* `ReStructuredText介绍 <https://docutils-zh-cn.readthedocs.io/zh_CN/latest/user/rst/quickstart.html>`_
* `reStructuredText 简介 <https://zh-sphinx-doc.readthedocs.io/en/latest/rest.html>`_
* `reStructuredText标记规范 <https://docutils-zh-cn.readthedocs.io/zh_CN/latest/ref/rst/restructuredtext.html>`_
* `reStructuredText入门 <http://www.pythondoc.com/sphinx/rest.html>`_
* `reStructuredText-Quick-Syntax <https://github.com/seayxu/CheatSheet/blob/master/files/reStructuredText-Quick-Syntax.md>`_

.. _my-reference-label:

--------
文本样式
--------

::

    * 斜体： *斜体*
    * 粗体： **粗体**
    * 行内代码： ``行内代码``
    * 分割符：

    ------

    注：粗体斜体行内代码前后需要空格，可以用\ 转义避免产生空格。
        分割符由大于4个 - 组成，前后需要添加换行。

* 斜体： *斜体*
* 粗体： **粗体**
* 行内代码： ``行内代码``
* 分割符：

-----

----
标题
----

标题使用符号 ``= - ` : ' " ~ ^ _  *  + # < >`` 表示，按照出现顺序自动分级。
::

    对于python文档，有一般约定：
      # 带上划线，表示parts。
      * 带上划线，表示chapters。
      = 表示sections。
      - 表示subsections。
      ^ 表示subsubsections。
      " 表示paragraphs。

标题示例
^^^^^^^^

使用=-^表示三个层级标题。

自动编号
^^^^^^^^

::

    .. toctree::
       :numbered:

----
段落
----

::

    空一行是表示新起一个段落。段落之间间距较大，若是有关联的换行，考虑\ **列表**\ 。

        可以使用缩进，表示缩进的段落。

            可以连续使用缩进

空一行是表示新起一个段落。段落之间间距较大，若是有关联的换行，考虑\ **列表**\ 。

    可以使用缩进，表示缩进的段落。

        可以连续使用缩进

----
列表
----

有序列表
^^^^^^^^

::

    1. 枚举的类型有:

        a. 阿拉伯数组: 1, 2, 3 ...
        b. 大小写字母: A-Z 或 a-z
        c. 大小写罗马字母: I, II, III, IV, ... 或 i, ii, iii, iv ...
    2. 使用 **#** 自动生成枚举序号，可以从任一数字开始

        4. xxx
        #. yyy
        #. zzz

1. 枚举的类型有:

    a. 阿拉伯数组: 1, 2, 3 ...
    b. 大小写字母: A-Z 或 a-z
    c. 大小写罗马字母: I, II, III, IV, ... 或 i, ii, iii, iv ...
2. 使用 **#** 自动生成枚举序号，可以从任一数字开始

    4. xxx
    #. yyy
    #. zzz

无序列表
^^^^^^^^

::

    * 可以使用 ``* + -`` 表示
    * xxx

        * 没有空一行的话，xxx会加粗; 反之不会
        * 缩进表示二级列表
    * 继续一级列表，不需要空行

* 可以使用 ``* + -`` 表示
* xxx

    * 没有空一行的话，xxx会加粗; 反之不会
    * 缩进表示二级列表
* 继续一级列表，不需要空行

--
块
--

文本块
^^^^^^

::

    ::

        上面的源代码部分就是采用文本块的形式呈现的。
        注意::下面要空一行。

::

    上面的源代码部分就是采用文本块的形式呈现的。
    注意::下面要空一行。

代码块
^^^^^^

pygments.lexers.get_all_lexers()可列出支持的代码类型。

::

    .. code-block:: python
        :linenos:

        def my_function():
            print('just a test', 8 // 2)
            print 8/2

linenos可以打开行号。

.. code-block:: python
    :linenos:

    def my_function():
        print('just a test', 8 // 2)
        print 8/2

文档测试块
^^^^^^^^^^

文档测试块是交互式的Python会话，以 >>> 开始，一个空行结束。

>>> print('This is a doctest block.')
This is a doctest block.


注解提示块
^^^^^^^^^^

::

    .. note::
        这是注解. note会执行(替换下面的#号)，但是单纯的文本块::不会。

        4. xxx
        #. yyy
        #. zzz

    块都支持缩进显示:

        .. Tip:: 这里是缩进的提示内容。


.. note::
    这是注解. note会执行(替换下面的#号)，但是单纯的文本块::不会。

    4. xxx
    #. yyy
    #. zzz

块都支持缩进显示:

    .. Tip:: 这里是缩进的提示内容。

行块
^^^^

::

    下面是行块内容：
    | 和缩进的区别
    | 间距是行距

    而缩进:

        缩进的间距是段落间距。

        上面这个间距很大。

行块使用|, 前后各有一个空格。

下面是行块内容：
 | 和缩进的区别
 | 间距是行距

而缩进:

    缩进的间距是段落间距。

    上面这个间距很大。

数学公式块
^^^^^^^^^^

::

    .. math::
        \ell(x, y) = L = \{l_1,\dots,l_N\}^\top, \quad
        l_n = \left( x_n - y_n \right)^2.

.. math::
    \ell(x, y) = L = \{l_1,\dots,l_N\}^\top, \quad
    l_n = \left( x_n - y_n \right)^2.

多行公式

.. math::
    \begin{align}
    a_{11}& = b_{11}& a_{12}& = b_{12}+c_{12}\\
    a_{21}& = b_{21}& a_{22}& = b_{22}+c_{22}
    \end{align}

----
链接
----

外部链接
^^^^^^^^
::


    详细内容请参考 `reStructuredText Primer <http://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html>`_。

详细内容请参考 `reStructuredText Primer <http://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html>`_。

内部链接
^^^^^^^^
::

    .. _my-reference-label:

    --------
    文本样式
    --------

    回到 :ref:`my-reference-label`。

回到 :ref:`my-reference-label`。

隐式超链接
^^^^^^^^^^

::

    标题、脚注和引用参考会自动生成超链接地址. 隐式链接到 `块`_。

标题、脚注和引用参考会自动生成超链接地址. 隐式链接到 `块`_。

----
图片
----

::

    .. image:: https://www.baidu.com/img/PCtm_d9c8750bed0b3c7d089fa7d55720d6cf.png
       :height: 300 px
       :width: 600 px
       :scale: 50 %
       :alt: 图片无法打开时显示
       :align: center

.. image:: https://www.baidu.com/img/PCtm_d9c8750bed0b3c7d089fa7d55720d6cf.png
   :height: 300 px
   :width: 600 px
   :scale: 50 %
   :alt: 图片无法打开时显示
   :align: center

----
表格
----

简单表格
^^^^^^^^

来自 `Open-ReID <https://cysu.github.io/open-reid/examples/benchmarks.html>`_ 的例子。

::

    ========= ============ ======== ============ ========== ==============
    Net       Loss         Mean AP  CMC allshots CMC cuhk03 CMC market1501
    ========= ============ ======== ============ ========== ==============
    Inception Triplet      N/A      N/A          N/A        N/A
    Inception Softmax      65.8     48.6         73.2       71.0
    Inception OIM          71.4     56.0         77.7       76.5
    ResNet-50 Triplet      **80.7** **67.9**     **84.3**   **85.0**
    ResNet-50 Softmax      62.7     44.6         70.8       69.0
    ResNet-50 OIM          72.5     58.2         77.5       79.2
    ========= ============ ======== ============ ========== ==============

========= ============ ======== ============ ========== ==============
Net       Loss         Mean AP  CMC allshots CMC cuhk03 CMC market1501
========= ============ ======== ============ ========== ==============
Inception Triplet      N/A      N/A          N/A        N/A
Inception Softmax      65.8     48.6         73.2       71.0
Inception OIM          71.4     56.0         77.7       76.5
ResNet-50 Triplet      **80.7** **67.9**     **84.3**   **85.0**
ResNet-50 Softmax      62.7     44.6         70.8       69.0
ResNet-50 OIM          72.5     58.2         77.5       79.2
========= ============ ======== ============ ========== ==============

网格表
^^^^^^

可以使用 `Tables Generator <https://www.tablesgenerator.com/text_tables>`_ 来生成。但是center不是很容易。

::

    +------------------------+------------+----------+----------+
    | Header row, column 1   | Header 2   | Header 3 | Header 4 |
    +========================+============+==========+==========+
    | body row 1, column 1   | column 2   | column 3 | column 4 |
    +------------------------+------------+----------+----------+
    | body row 2             | Cells may span columns.          |
    +------------------------+------------+---------------------+
    | body row 3             | Cells may  | - Table cells       |
    +------------------------+ span rows. | - contain           |
    | body row 4             |            | - body elements.    |
    +------------------------+------------+---------------------+

+------------------------+------------+----------+----------+
| Header row, column 1   | Header 2   | Header 3 | Header 4 |
+========================+============+==========+==========+
| body row 1, column 1   | column 2   | column 3 | column 4 |
+------------------------+------------+----------+----------+
| body row 2             | Cells may span columns.          |
+------------------------+------------+---------------------+
| body row 3             | Cells may  | - Table cells       |
+------------------------+ span rows. | - contain           |
| body row 4             |            | - body elements.    |
+------------------------+------------+---------------------+

--------
脚注引文
--------

脚注
^^^^

可以使用 ``[#name]_`` 标注在脚注的位置，在文档的最后的 ``.. rubric::`` 参考文献 后添加脚注的内容。

::

    Lorem ipsum [#f1]_ dolor sit amet ... [#f2]_

    .. rubric:: 参考文献

    .. [#f1] 这是第一个参考文献。
    .. [#f2] 这是第二个参考文献。

你也可以明确用数字标注脚注或者通过不指定 name 使用自动数字标记脚注 ``([#]_)`` 。

Lorem ipsum [#]_ dolor sit amet ... [#]_

引文
^^^^

Sphinx支持标准reST引文(ref)，增加了所有引文是“全局的”的特性，即：所有的文件可以使用所有的引文。这样使用它们:

::

    Lorem ipsum [Ref]_ dolor sit amet.

    .. [Ref] Book or article reference, URL or whatever.

Lorem ipsum [Ref]_ dolor sit amet.

.. [Ref] Book or article reference, URL or whatever.

引文用法是类似的脚注的用法，但带标签不是数字，或以``#``开始。

----
注释
----

不是一个有效的标记结构（如上述的脚注）的每一个明确的标记块被视为一条评论。

::

    .. This is a comment.

可以缩进文本在注释开始后，这样可以形成多行注释:

::

    ..
       This whole indented block
       is a comment.

       Still in the comment.

.. rubric:: 参考文献

.. [#] 这是第一个参考文献。
.. [#] 这是第二个参考文献。
