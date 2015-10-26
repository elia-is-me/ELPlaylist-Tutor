#ELplaylist 教程（一）

##前言

Elplaylist 是由 **ssenna** 写的一个高级播放列表插件，作者 ssenna 是一个日本人，他（她）同时也是*面板栈分离器*、*albumlist*等插件的作者，而这几个插件可以说是 fb2k界面配置中使用率最高的几个插件了，可以说 90% 的 fb2k 配置都是 cui + elp+ pss 为主的。直到这两年，用 wsh playlist 去代替 elplaylist的配置才稍微多一点，而 wsh playlist的修改难度可以说非常非常大，而原创一个 wsh playlist简直逆天。相比之下，elplaylist的功能强大，配置也算比较灵活，并且由于其配置脚本是 title formatting形式的，title formatting（标题格式化脚本）的难度就很一般了，完全可以拿到台面上来讲。

本人（百度ID：Elia\_is\_me）早前曾经做过一个 elplaylist 的教程，尽管仓促却也够详细，不过后来 ID 被封帖子也不再可见，去年（2013年）还能找到网页快照，今年则完全无影无踪了，所以顺便就重写一个。为了防止再次因为ID 被封导致帖子找不到，所以这次会保留离线版，可能还会上传到 GitHub上，被删的风险应该没有了。

教程预计主要为两个部分：（一）为设置界面的介绍以及一些常规设置；（二）则主要介绍脚本。教程的目的不是为了教你做出多么多么漂亮的界面，而是告诉你elplaylist的配置的方法，这样当你有想法的时候可以随时参考做出适合你自己的界面出来。**要注意的是elplaylist 的界面配置的难度可能是仅次于 wsh panel mod 和面板栈分离器的**，所以如果一遍没看懂什么的很正常，多看几遍，多练习是关键。如果仅仅抱着*“花几分钟时间做出个漂亮的界面”*的心态的话，可能 elplaylist 不适合你。

为了简便起见，下面的内容中可能会出现一些缩写，提前列出：

> * elp : Elplaylist （Elplaylist 播放列表）
> * cui : Column UI （分栏界面）
> * fui : Func UI 
> * pss : Panel Stack Splitter （面板栈分离器）
> * wshm : Wsh Panel Mod （Wsh 面板改进版）
> * tf : title formatting（标题格式化脚本语言）

##准备工作

ELP 只能在 CUI 界面下使用（FUI未知），所以如果要用 elp 的话首先需要对 cui 有些了解才行，所以先贴两个 CUI 的教程，这样你才能把 elp 面板放到 cui 界面上：

> * [Wosgar：Foobar2000音乐播放器教程（三）—— 皮肤修改](http://tieba.baidu.com/p/2711054973)
> * [伏天：【初级教程-界面】--简单分栏用户界面（CUI配置）的制作--](http://tieba.baidu.com/p/2093606833)
> * [伏天：【进阶教程-界面美化】----分栏用户界面CUI的制作与修改](http://tieba.baidu.com/p/2237071201)

本人会给出一个练习用的懒人包，里面精简了不需要的插件，仅保留练习所需要的插件，不能播放无损音乐，不适合日常使用，请注意。

> * [下载地址](http://pan.baidu.com/s/1gd7qkpl)

其次，elp 的配置脚本是 **tf 语言**，所以如果要给 elp 写脚本，必须对 tf有一定的了解。Tf使用起来非常非常简单，只有**字段**和**函数**两种数据类型，tf 的帮助在fb2k `主菜单：帮助 > 标题格式帮助` 可以找到。

最后，elp 的[英文帮助说明文件](http://wiki.hydrogenaud.io/index.php?title=Foobar2000:Components_0.9/ELplaylist_panel_%28foo_uie_elplaylist%29)，
懂英文的话直接查询帮助会方便许多。


##设置界面

设置界面调出方式很简单：`右键 > 设置`：

![image](https://raw.githubusercontent.com/elia-is-me/ELPlaylist-Tutor/master/images/img-1.png)

会看到设置界面有**五个**主标签页：`脚本`、`样式`、`分组`、`字段定义`、`行为`、`杂项`。ELP 的全部设置都在这五个标签页下面，下面会分别介绍这五个标签页下的设置选项。因为本教程设定为写给初学者的参考教程，所以可能有些设置会被省略。不要紧的，等你需要用那些设置选项的时候你应该对设置 elp 很熟悉了。

###“脚本”：

`脚本`标签页下是你编辑脚本的地方，有五个子标签页，暂时不介绍，因为后面会专门介绍怎么编写脚本。

这里要注意的只有`标题格式化脚本预设`，这里显示的是脚本名，你可以新建多个脚本，也可以给已有的脚本重命名：

* 点`新建`按钮就会新建脚本，新建的脚本内容会与你当前脚本的内容完全相同；
* 通过下拉选项切换到你想重命名的脚本名，重新输入新的脚本名，然后点`重命名`就会更新当前脚本的名称；

>如果你不理解我上面说的是什么，那么你就照着我说的去操作几次，应该就能理解我的意思。这句话我后面不再加，但希望你记住。

在界面最下排，有一排按钮，其中：

1. 重设：会清除你的所有设置，恢复到默认设置，请谨慎；
1. 导出：导出你的设置到 `xxx.elp` 文件；
1. 导入：将`yyy.elp`的配置文件导入到当前的 elp 中；

其它的就不说了。

###“样式”

![image](https://raw.github.com/elia-is-me/ELPlaylist-Tutor/master/images/img-2.png)

这里是设置界面颜色、外观等的地方。在这里`边缘样式`、`仿真透明`、`滚动条`的设置不会被`脚本`设置覆盖，而`背景颜色`、`外观样式`则可能被脚本里的设置覆盖掉，比如你在脚本里如果也设置了背景色之类的东西，那么在这里的设置就无无效了。

给一张设置的效果示意图：

![image](https://raw.github.com/elia-is-me/ELPlaylist-Tutor/master/images/img-3.png )

`自定义背景颜色`下面的左、右填充只对自定义的背景颜色起作用；而`启用外观样式`下面的左、右填充则只对外观样式（正在播放和选定的项目会有一个半透明的系统样式的背景填充）起作用。

**滚动条**的显示/隐藏在滚动条后面的下拉菜单设置。

再次强调：这里面无论是`默认字体`，还是`自定义背景颜色`，还是`外观样式`都被脚本所替代，所以这里你可以只设定`边缘样式`，`仿真透明`和`滚动条`，怎么方便就怎么来。

###“分组”（重要）

先介绍“分组”的概念：就是将符合同样的条件的歌曲归类在同一组下面，在显示
的时候显得更加有条理一些。比如：

![image](https://raw.github.com/elia-is-me/ELPlaylist-Tutor/master/images/img-4.png)

这个例子，就是将播放列表的内容按照“艺术家”分组。

常用的分组格式：

* %artist%：按`艺术家`分组；
* %album artist% - %album% - %discnumber%：按照`专辑艺术家 - 专辑 - 碟片号`分组，这是最常用的；
* $directory_path(%path%)：按`文件所在文件夹`分组；
* %date%：按`时间`分组，如果你的歌曲时间都是年份开头的话也可以是 $left(%date%,4)，按`年份`分组；
* %rating%：按`评级`分组；

当然，你也可以自己定义分组格式，怎么奇葩都可以。另外，如果你的列表里的歌曲都是散歌，毫无规律可循的话，那么就不适合分组，分不分组是按需要来的。


1. 在这个标签页里，最上面是`新建`、`删除`、`重命名`分组样式，操作方法都是很简单的。你可以新建多个分组样式，并分别设置不同的分组样式，这样就可以通过`右键：分组按`来切换分组样式了。
![image](https://raw.github.com/elia-is-me/ELPlaylist-Tutor/master/images/img-5.png )

1. `分组格式`就填上面提到的那些，`排序格式`看情况填。

1. `行高`：elp 中每首歌占一行，每一行的高度在这里定义。

1. `分组行数`：`分组行高 = 分组行数 * 行高`。这里可以是一个固定的数字，比如`4`，也可以加一个判断语句：`$if(%el_is_collapsed%,3,4)`, 比如这个例子表示当分组折叠起来的时候，分组行高就就变成`3 * 行高`了，如图示：
![image](https://raw.github.com/elia-is-me/ELPlaylist-Tutor/master/images/img-6.png )

1. `最小分组行数`：设置每一组的最小行数（不是分组标题栏而是下面的歌曲所占的行）。在有些时候会比较有用，比如如果你在侧面显示专辑封面，如果这一组歌曲太少的话可能封面就显示不全，但设置了最小行数的话就可以保证有足够的空间给你放专辑封面。
![image](https://raw.github.com/elia-is-me/ELPlaylist-Tutor/master/images/img-7.png )

1. `播放列表过滤`：可以针对特定的播放列表，自动判断是否分组，使用哪一个分组，功能挺强大，不过细节并不完美，因为比较高级所以就不介绍了。可以自己试一试。

1. `关联标题格式化脚本`：记得前面`脚本`标签页下新建的脚本吗？在这里可以选择不同的分组关联不同的脚本样式，使得不同的分组时 elp 的界面显示完全不同。

###“字段定义”

这里是定义全局字段用的，如果你学过编程的话就很容易懂这其实是“宏”，跟 c 语言中的 `#define` 很像。定义好的字段用 `%var_name%` 引用，在你写脚本的时候。

有些值可能你写脚本的时候会经常用到，比如背景色设为 `200-200-200`，把背景色定义为 `%back_color%`, 然后写脚本的时候如果要写 `200-200-200` 的地方就全用 `%back_color%` 代替。

这样做的目的并不是为了让你少打几个字，尽管可能有这个作用。真正的目的是为了让脚本更加好读懂，

字段可以是数字、字符串甚至是 tf 函数。

![image](https://raw.github.com/elia-is-me/ELPlaylist-Tutor/master/images/img-8.png)

###“行为”

这里是 elp 的一些行为的地方，选项很多但大部分不需要修改。

1. 点击操作：默认就行了，不要改，基本不需要。

1. 鼠标悬停操作：启用的话当鼠标悬停在曲目行是会弹出一个歌曲信息的界面。

1. 每秒更新一次：如果你希望列表播放时显示一些动态的内容的话，比如**播放进度**之类的，你可以勾选上，这个是会消耗 cpu 资源的，根据自己电脑量力而行。当然 elplaylist 效率相当高，勾选上基本没事。

1. 调整质量：默认就行。

1. 上下文菜单：右边有个复选框，如果你勾上的话，那么这个菜单选项就会在右键菜单
中显示，如果不勾上的话右键菜单就没有。

###“杂项”

也不怎么需要设置，`悬停窗口`那里根据自己需要设置，都是汉字应该不难看懂。

`附加排序格式到上下文菜单` 可以自己设置`右键：排序`菜单下面的子菜单项。

![image](https://raw.github.com/elia-is-me/ELPlaylist-Tutor/master/images/img-9.png)

![image](https://raw.github.com/elia-is-me/ELPlaylist-Tutor/master/images/img-10.png)

## 结语

*教程（一）*就到这里，主要就是介绍 elp 的设置界面。还是有点复杂的，新手可能一开始看不懂，所以多看几次，不光是教程，还有实例。多看多试几遍后就应该知道怎么回事了。

不要没有耐心，如果你真的要自己做一个 elp 的样式的话，看我的教程是不够的，英文的说明文档也是必看。[foobar2000 中文论坛](http://www.foobar2000.com.cn) 还有**neon**的[翻译文档](http://www.foobar2000.com.cn/read.php?tid-17159.html)，不过他（她）设置了回复可见，而论坛又不准回复……不过好在 **Asion** 那儿有，所以让他给我传了一份，我附在文章的结尾了[1]。

话说回来，如果有兴趣的话，多看几遍又何妨？本人对 Jscript 一窍不通，看了一遍又一遍的 wsh 文档，终于还不是“七窍通了六窍”？

## 注解

Elp 自带的字段和函数都没有介绍，虽然文档中有，但在这篇教程中有用到的话，就加点说明在这里吧：
> * %el_is_collapsed%: 判断分组是不是折叠起来的，仅仅在`分组标题`和`分组行数`中有用。
> * %el_width%: 返回行宽，在`音轨列表`、`分组标题`、`每秒更新`、`悬停`中可用。
> * %el_height%: 在“脚本”标签页下的各个标签页都可用，举例说明：
```
 `行高`设为28，`分组行数`设为 3 的话，那么在各个标签页下：
 默认或者 $setworldtransform(0) 时：
 `音轨列表`中，`%el_height% = 28
 `分组标题`中，`%el_height% = 28 * 3
 如果 `$setworldtransform(1)` 时：
 `%el_height% = (%el_item_count2% + %el_group_row%) * %el_row_height%`
 如果 `$setworldtransform(2)` 时：
 `%el_height% = %el_item_count2% * %el_row_height%`
```

> * %el_row_height%: 行高
> * %el_item_count2%: 列表中非空的行数（英文文档似乎有误）

##参考资料
1. Elp 文档 翻译 by neon):
  https://raw.githubusercontent.com/elia-is-me/ELPlaylist-Tutor/master/text-files/elp_chs.txt
1. Wiki: [Foobar2000:Components 0.9/ELplaylist panel (foo uie elplaylist)](http://wiki.hydrogenaud.io/index.php?title=Foobar2000:Components_0.9/ELplaylist_panel_%28foo_uie_elplaylist%29#.25el_height.25)
1. Shutter by Jensen & dreamxis: [dreamxis 的博客地址](http://dreamxis.themex.net/709)

## 鸣谢

感谢 Asion 提供了 elp 的中文文档资料，感谢 neonasahi 的翻译工作，因为前人的努力，使得我工作轻松不少。

