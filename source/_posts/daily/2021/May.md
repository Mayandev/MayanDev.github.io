---
title: 2021 年 5 月
date: 2021-05-22 10:36:00
tags: 
  - 日常
categories: 日常记录
---

## 5 月 22 日

这个月快过完了，我突然想重新建一个网站，来记录自己的生活和工作日常，收录一些平时工作中查询的文章、工具、问题等等。折腾来，折腾去，试用了很多的现代的 Static Site Generate 框架，觉得还是没有 Hexo 博客来的方便。现在这些框架非常裸，自定义能力很高，很多功能都需要自己写代码完成，但是我并不想花费太多时间在这些配置上。

于是就在博客开一个新的分类，就叫做[日常记录](https://blog.mayandev.top/categories/%E6%97%A5%E5%B8%B8%E8%AE%B0%E5%BD%95/)吧。

顺便记录一下昨天看到的内容。

### 命令

```bash
> git mv -f oldfilename newfilename
```

这个命令可以在保持 git commit 提交记录的情况下，对文件进行重命名，昨天 ts 重构时有用到

### 文章

- [如何使用 ts 正确姿势的定义 defaultProps](https://medium.com/@martin_hotell/react-typescript-and-defaultprops-dilemma-ca7f81c661c7)

### 新闻

今天最大的新闻是[袁隆平去世](http://www.xinhuanet.com/photo/2021-05/22/c_1127478719.htm)了，记得小学的课本上就学过关于他的课文，都说他救活了中国人。我家以前家里穷，吃不起啥东西，所以一向比较节俭，不会浪费粮食，勉强也算是对袁老的一种尊重吧。

## 5 月 23 日

### 单词

今天某个 MR 的描述里面写到「下线」某个页面，用了短语 「take down」，被指出用词不太准确，应该使用 「sunset」，然后 mentor 举了一个很生动的例子。

> take down: 打倒阶级敌人
> sunset: 送走老朋友

### Snippet

- [一段 JavaScript 代码](https://codepen.io/mayandev/pen/zYZZXoX?editors=0011)，用于将 Map 的 key 和 value 进行互相转换。

```javascript
const reverseMapKeyValue = (o) => Object.keys(o).reduce((r, k) => Object.assign(r, {[o[k]]: k}), {})
const object = {foo: 'bar'};
console.log(reverseMapKeyValue(object)) // {bar: 'foo'}
```
### 文章

- [An Introduction to Knowledge Graphs ｜ 知识图谱介绍](http://ai.stanford.edu/blog/introduction-to-knowledge-graphs/)

### GitHub

- [daisyUI](https://github.com/saadeghi/daisyui)，一个很漂亮的 Tailwind CSS 组件库，压缩后仅仅 2kb



## 5 月 24 日

### 网站

- [https://schemeflood.com](https://schemeflood.com)，这个网站很有意思，可以检测你电脑安装了那些应用。原理很简单，利用浏览器的 Url Scheme 功能，监听是否打开新的窗口。比如当打开 TG 频道页面时，浏览器自动弹出一个提示框让用户决定是否打开客户端，但是如果没有安装该客户端，那么就不会出现这个提示框。通过收集的数据，可以对用户进行一个很好的画像处理。当然，这样的检测肯定是不完整的，因为不是所有的网页都做了 App 启动的功能。



