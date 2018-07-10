layout: page
title: Indigo
description: 用户自定义页面功能演示

---

## Image

![image](//placekitten.com/1000/500)

## Blockquote

> 当`blockquote`、`img`、`pre`、`figure`为第一级内容时，在`page`布局中拥有`card`阴影，所有标题居中展示。

## Content

@card{

目前的想法是预定义一系列内容模块，通过像输入 Markdown 标记一样来简单调用。好在 Markdown 没有把所有便于输入的符号占用，最终我定义了`@moduleName{ ... }`这种标记格式。如果你使用过`Asp.Net MVC`，一定会很熟悉这种用法，没错，就是`razor`。

`page`布局中的`title`和`subtitle`对应 Markdown 中的`title`和`description`。

基本的内容容器还是`card`，你可以这样使用`card`：

```css
@card{

在`page`页中，建议把内容都放到`card`中。

}
```

需要注意的是：**标记与内容之间必须空一行隔开。**至于为何要这样，看到最后就明白了。

}

## Column

@column-2{

@card{

### 左

与`card`标记类似，分栏的标记是这样的：

```css
@column-2 {
  @card {
    #左;
  }

  @card {
    #右;
  }
}
```

> 为了移动端观感，当屏幕宽度小于 480 时，`column`将换行显示。

}

@card{

### 右

`column`中的每一列具有等宽、等高的特点，最多支持三栏：

```css
@column-3{

@card{

左

}

@card{

中

}

@card{

右

}

}
```

}

}

## Three columns

@column-3{

@card{

话式片平九业影查类办细开被支，置军争里老 5 备才才目板。 且数置百容机，规的空界往，十陕志入。料解格清收权厂值动且习，识生能化路速年边，类儿 2 带杏性热求已。

}

@card{

话式片平九业影查类办细开被支，置军争里老 5 备才才目板。 且数置百容机，规的空界往，十陕志入。料解格清收权厂值动且习，识生能化路速年边，类儿 2 带杏性热求已。

}

@card{

话式片平九业影查类办细开被支，置军争里老 5 备才才目板。 且数置百容机，规的空界往，十陕志入。料解格清收权厂值动且习，识生能化路速年边，类儿 2 带杏性热求已。

}

}

## Timeline

@card{

在`timeline`模块中，你的 5 号标题`#####`和六号标题`######`将被“征用”，用作时间线上的标记点：

```css
@timeline {
  ##### 2016 @item {
    ######11月6日 为 Card theme 添加 page layout。;
  }
}
```

`@item`中多行内容可以换行输入，目前不允许隔行：

```css
@timeline {
  ##### 2016 @item {
    ######11月6日 第一行 第二行 /* ok */;
  }

  @item {
    ######11月6日 第一行 第二行 /* error */;
  }
}
```

}

@timeline{

##### 2016

@item{

###### 11 月 6 日

为 Card theme 添加 page layout。
加快绿化空间好看

}

@item{

###### 10 月 31 日

本地化多说。

}

@item{

###### 10 月 24 日

为 Indigo 主题创建 Card 分支。

}

##### 2015

@item{

###### 2 月 24 日

发布 Indigo 主题到 hexo.io。

}

@item{

###### 1 月 22 日

创建 Indigo 主题。

}

}

## CodeBlock

```js
// 自定义内容块实现
page.content
  .replace(/<p>}<\/p>/g, "</div>")
  .replace(/<p>@([\w-]+){<\/p>/g, function(match, $1) {
    return '<div class="' + $1 + '">';
  });
```

@card{

这里可以解释，为什么标记之间必须要隔一行了。

当你在 Markdown 中隔行输入时，会形成新的段落，而如果一个段落中的内容仅仅是我们约定的标记，就可以用很容易的用正则匹配到替换为对应的`模块容器`。

}

## End

@card{

为了解决 Hexo 自定义页面`slug`为空不能很好的使用多说评论这个问题，现在已经给每个自定义页面自动生成了`hexo-page-path`这种格式的`slug`。
本来准备用`date`做格式的最后一节，测试中发现 page 中的`date`值为修改时间，是动态的。
综合考虑使用了路径`path`。

以后可以根据需要添加更多模块支持。

打赏和评论默认开启，可根据需要在 Markdown 头部定义是否关闭。

}
