# 常用选项

> 一些选项在大部分程序中都是通用的。为避免在每个程序章节都描述相同的内容，所以编写了这节内容（事实上，每个GNU程序都接受（或应该接受）这些选项）

正常情况下，选项和操作数（options and operands）可以在任意位置，程序会把选项放到所有操作数前面。例如，'`sort -r passwd -t :`' 会被转换成 '`sort -r -t : passwd`'，因为 '`:`' 是选项'`-t`'的参数。无论如何，如果设置了 '`POSIXLY_CORRECT`' 环境变量，则选项必须在操作数之前，除非其他命令另有规定

A few programs can usefully have trailing operands with leading ‘-’. 使用这样命令的时候，即使没有设置 '`POSIXLY_CORRECT`' 环境变量，选项也必须出现在操作数之前，这些事项会在程序的描述文档中记录。例如，'`env`' 命令的选项必须出现在操作数之前，因为在一些情况下，操作数指定了一些他自己的选项。

大多数接受长选项的程序也识别这些选项的明确缩写。例如：'`rmdir --ignore-fail-on-non-empty`' 也可以写成'`rmdir --ignore-fail`'或者 '`rmdir --i`'。含糊的选项也如此，例如：'`ls --h`'

一些程序在 '`--help`'和'`--version`'只有其中一个是他们接受的命令行参数时才会识别这些选项。对于这些程序，长选项的缩写不是经常被识别的。

* '`--help`'
> 打印所有可用选项的使用信息，然后成功退出

* '`--version`'
> 打印程序的版本号，然后成功退出

* '`--`'
> 分割选项列表，后面的参数即使以 '`-`' 打头，也被当做操作数。例如：'`sort -- -r`'去读取名字是 '`-r`'的文件内容。

单独的操作数 '`-`'并不是一个选项，尽管它看起来很像。它代表标准输入，或者在明确的上下文下，也可以是标准输出。例如，'`sort -`'