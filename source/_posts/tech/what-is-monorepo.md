---
title: 什么是 Monorepo
date: 2021-02-22 16:36:00
tags: 
  - 前端
  - Git
  - Monorepo
categories: 前端
---

> 今天看到团队有人说项目要迁移为 Monorepo，作为小白的我还是头一次看见这个词，好奇心的驱动下 Google 了一番，才知道原来 Monorepo 不是一种新的技术，而是代码库的一种组织方式。

看到一篇 Perforce 上一篇不错的介绍文章，翻译一下。

原文地址：https://www.perforce.com/blog/vcs/what-monorepo

---

## 什么是 Monorepo，你为什么要关心

Monorepo 意思是是单一的资源库，它存储了每个项目的所有代码和以及资源，它使代码共享更容易，甚至使重构代码变得更容易。

## Monorepo & Monolith 之间的不同

Monarepo 是一个单一的仓库，而 Monolith 是一个庞大的代码库。

Monarepo 可以用一个 Monolith 管理。但是，一个 Monolith 也可以被分割成多个仓库。同样，一个 Monarepo 也可以用微服务来代替 Monolith。

在本篇博客中，我们将重点介绍 Monorepo。

## Monorepo vs. Multirepo

monorepo 将所有的东西都保存在一个版本库中。多仓库（multirepo）通常每个项目都有一个仓库。项目越多，仓库越多。multirepo 也被称为 polyrepo。

那么，哪一个更好呢？你应该把所有的东西都集中在一个仓库里吗？还是应该把它分成多个仓库？

### Monorepo通常适合：

#### 1.可见度
使用单一的存储库可以让你看到每个项目的代码和资源，这有助于管理依赖性。

#### 2.协作
单一的存储库让协作变得更容易。因为每个人都可以访问代码、文件和资源。因此，开发人员可以共享和重用资源。

#### 3.速度
使用单一的存储库可以帮助你加速开发。例如，你可以进行原子式的更改（一个动作在多个项目中进行更改）。

### Multirepo 通常适合：

#### 1.Git项目

在Git中大规模管理一个 monorepo 是行不通的。随着仓库越来越大，Git 中的monorepo就会成为一个巨大的问题。所以如果你有团队使用Git，最好有多个仓库。


#### 2.开放源码或第三方项目

在一些版本控制系统中，你需要多个仓库来使用开源项目或与第三方团队合作。那么你就可以确保第三方开发人员只能访问他们正在进行的项目。

## 所以，为何要使用 Monorepo

对许多公司来说，使用 Monorepo 是个好主意。你可以将每个团队的所有源代码（以及其他文件/数字资产）保存在一个存储库中。这使得它更容易与每个人分享。而且它可以帮助你维护一个单一的真实来源。

在任何提交之后，新的代码对所有开发者都是可见的，这有助于避免基于主干的开发中普遍存在的痛苦的合并。

以下是你应该考虑使用 Monorepo 的一些原因。

- 你想要一个单一的真实来源。
- 你想轻松地共享和重用代码。
- 你想要管理依赖关系的可见性（例如，如果你做了一个改变，还有什么会受到影响？
- 你想进行原子式的变更（例如，一个操作就可以在多个项目中进行变更）。
- 你希望团队能更多地协作。
- 你想进行大规模的变更（例如，代码重构）。
- 如果你决定走 Monorepo 路线，你将会是一个好公司。领先的公司--比如Google--使用的是monorepo。  

下面就不翻译了，是推销网站自己的版本控制软件。

---

另外 [CSS Trick 的一篇文章](https://css-tricks.com/monorepo/)中也介绍了相关的优缺点，归纳的比较全面和客观。

## Monorepo的优势(对我们来说)
- 一环定乾坤。你用 git 拉一个 repo，你就能 100% 跟上其他人的进度，并且拥有一个完整的开发环境。
- No stray puppies（不知道咋翻译这个😂）。在 GitHub 上，不会出现混乱。您可以针对 monorepo 发起 Pull Request。您可以在 monorepo 上打开 issues。这就避免了分散的活动被丢失。
- 欢聚一堂。你可以分享代码。在代码库中的任何地方共享实用程序或组件都会特别有用。我们曾尝试过将共享位发布到 npm 上供其他仓库使用的想法，但与将代码放在一起相比，这样的工作流程很不方便。
- 一起变老。没有老旧和被忽视的repos，因为它只是一个。对于我们这个小团队来说，拥有几十个repos 意味着其中一些 repos 有老旧过时的依赖，有古老版本的 Node，有与其他 repos 不同步的 linting 和格式化规则等等。

## Monorepo的缺点(对我们来说)

- 部署变得棘手。我们最初拆分repos的主要原因是，这些 repos 中的代码需要去到部署到不同的地方。它们可能代表了其他服务器上的一个单独的服务。一个单独的 repo 意味着更容易挂上该服务器/服务特有的东西，比如CI/CD。
