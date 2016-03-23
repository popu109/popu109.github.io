---
layout: post
title: 使用ghpages+Jekyll免费做博客
---

Index
-
这次，我们说的是用github pages服务和Jekyll这个开源程序做博客的方法，尽管教程很长，但是别担心，大部分时间(~~我都是在瞎bb~~)都没有什么难点，只是需要一点耐心而已。注意，在开始操作之前，务必完整地看一遍教程哦。
相关：

> Github:https://github.com
> Jekyll:https://github.com/jekyll/jekyll
> Freshman21:https://github.com/yulijia/freshman21
> Freshman21-JFLS:https://github.com/jiwairen/blog-freshman21

下面正片开始：

准备阶段
-
**一切的开始，你得有个github账号**
首先，打开[Github的注册页面](https://github.com/join)
这注册很简单不是么？
如果连Username，Email Address，Password，Create an account都不懂的话，个人推荐你戳关闭
唯一需要注意的，是第二步选择plan的时候，切记选Free哟~（你不是程序猿买了专业版也没啥用）
最后不要忘记到邮箱去收验证邮件，里面有链接要点进去神马的不用我说了吧？

**然后的然后，叉(fork)一个Jekyll博客模板过来**
>记得验证完邮箱再做这步哦

1.打开[freshman21的项目页面](https://github.com/jiwairen/blog-freshman21)

2.轻轻地~~插~~叉它一下，没错，就是戳右上角那个fork。
![](http://ww3.sinaimg.cn/mw690/ec922a76jw1f0fo02y5dsj20tn02wt8p.jpg)

3.戳完之后你应该会发现左上角的标题已经从`jiwairen/blog-freshman21`变成了`你的用户名/blog-freshman21`这就对了~

4.打开Settings选项卡，把Repository name改成`你的用户名.github.io`
![](http://ww2.sinaimg.cn/mw690/ec922a76jw1f0fo4ye3ufj20jx078dg5.jpg)


**最后的时间，设置一下博客吧~**
1.让我们来到code选项卡，点开`_config.yml`文件，里面就是我们网站的设置啦~格式和单词很简单呢随意修改即可(别忘记在英文冒号后面有空格)~
下面是推荐修改的内容和说明：
```
title: #网站标题
tagline: #副标题
author: #站长，也就是你的名字
email: #你的邮箱
url: #网站地址，切记带上前面的http://哦
duoshuo: #是否启用多说，一个在国内更快但难看的评论系统,true启用/false禁用
aboutme: #关于你的介绍
aboutme_photo: #你的图片
default_column: "one" #网站使用单栏还是双栏的风格，可以修改为two看看效果，再决定使用哪种
```
接下来这步是最后一步了，在项目页面戳new file新建一个文件，在上面的文件名中输入`CNAME`，内容框中输入`xxx.jiwai.ren`（就是你要用的域名啦~比如我的就是[test.jiwai.ren](http://test.jiwai.ren)）
![](http://ww3.sinaimg.cn/mw690/ec922a76jw1f0foeryxayj209h03ya9y.jpg)
然后点击下面的绿色按钮保存
![](http://ww1.sinaimg.cn/mw690/ec922a76jw1f0fofl0pvjj20k709bmxe.jpg)

***

写作开始
-
现在就可以开始写作啦～
**基础知识**
Jekyll的文章都是以文件的方式保存在_posts目录下的
文件名有着严格的格式：`YEAR-MONTH-DAY-title.MARKUP`
其中year，month，day表示博文的发表日期，当然你可以随便写；title即博文的英文标题，将会出现在链接里，最好是e文，可以有减号，不能有空格；markup表示这篇文章的格式，通常是markdown，下面的语法教程也将是markdown，这里可简写为md。
**博主建议**
个人推荐在本地环境中写作并与写完之后发到网站上，当然你文思泉涌一次写一篇毫无鸭梨的话当我没说。
前期不熟悉md的时候可以用一些支持md的编辑器，而一般情况用普通的文本编辑器就好了。
下面是一些不错的编辑器
|名称|平台|有无markdown|特点|
|--|--|--|--|
|记事本|Win|无|系统自带|
|notepad++|Win|无|简洁轻量|
|atom|Win+Mac+Linux|有|炫酷实用，但略卡|
|Sublime Text2|Win+Mac+Linux|有|极受欢迎的代码编辑器，挺好看的|
|OneNote|PC+移动全平台|无|云笔记，全设备同步，微软出品|
|xx云笔记|通常Win+安卓iOS|通常无|各有所长，可根据个人需求选择|

**写作时间**
在文档的头部，应该写有这篇文章的基本信息（名字，作者等），这个头信息格式我们叫它YAML。
在jekyll中，应注意几点的如下：
1.使用三个减号来包裹头信息。
2.务必将头信息放在文件头部。
格式范例：
```
---
layout: post
title: I'm a sb
---
```
如你所想的那样，有一些设置变量是系统定义过的：
|变量名|文字说明|
|--|--|
|`layout`|指定模板。模板文件需要放在 _layouts 目录下。
|`permalink`|如果你想让你的这篇文章的网址不同于默认的 `/标题.html` （如变成Youaresb.html），那么当你设置这个变量后，就会使用这个URL地址。
|`published`|如果你要隐藏这篇博文，可以设置这个变量为 false。
|`category` or `categories`|除过将博客文章放在某个文件夹下面外，你还可以根据文章的类别来给他们设置一个或者多个分类属性。这样当你的博客生成的时候这些文章就可以根据这些分类来阅读。在一个文章中多个类别可以通过 YAML list来指定，或者用空格隔开。
|`tags`|类似分类，一篇文章也可以给它增加一个或者多个标签。同样多个标签之间可以通过 YAML 列表或者空格隔开。

***

万事俱备，只差文章！
-
首先，进入到_posts目录下，戳new file新建一个文件。
按照YEAR-MONTH-DAY-title.MARKUP的格式填写文件名，为其填写YAML头，并以Markdown格式创作文章内容（Markdown的讲解放在另一篇文章中），最后保存即可。稍等片刻，刷新就能看到新文章了~

***

>本文参考：
>http://jekyllrb.com
>https://github.com

***

技术中心 - 济外人网站联盟计划

