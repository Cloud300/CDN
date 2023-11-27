---
title: CDN加速博客访问
date: 2020-08-31 17:23:33
tags: [CDN,Hexo,笔记]
cover: https://cdn.jsdelivr.net/gh/Cloud300/Picture-bed/blog_pic/紫禁城的雪.jpg
categories: 笔记
thumbnail: https://cdn.jsdelivr.net/gh/Cloud300/Picture-bed/blog_pic/小预览01.png
---

## 前言😄

**CDN** 的全称是 **Content Delivery Network**，即内容分发网络。

**CDN** 是构建在网络之上的内容分发网络，依靠部署在各地的边缘服务器，通过中心平台的负载均衡、内容分发、调度等功能模块，使用户就近获取所需内容，降低网络拥塞，提高用户访问响应速度和命中率。

**CDN** 的关键技术主要有内容存储和分发技术。放在 **Github** 上的资源在国内加载速度比较慢，因此需要使用**CDN**加速来优化网站打开速度 **Jsdelivr/CDN** 便是免费好用的**CDN**，非常适合博客网站使用。

<br>

## 2023/11/27日更新🤣🤣

使用**PICGO**软件，使用**Github**作为仓库，设置好对应的参数后，直接把压缩后的图片拖进去，重命名上传，之后引用链接即可😂😂

1、  首先新建一个Github仓库，仓库名自定义

2、  生成token（计算机术语，令牌）

3、  **Github**右上角头像处→设置→列表里的：**Developer settings → personal access tokens** → 选择：**Generate new token**（生成新令牌）

![](https://cdn.jsdelivr.net/gh/Cloud300/Picture-bed/blog_pic/token2.png#pic_left)

![](https://cdn.jsdelivr.net/gh/Cloud300/Picture-bed/blog_pic/token2.1.png#pic_left)



4、  下面是仓库权限，都勾上即可

5、  然后最下边绿色的框框，生成令牌

6、生成之后即可看到**token**页面，它只会显示一次，**复制令牌保存**🚩到文档里，一会配置PicGo要用<br>

## 配置PicGo🍦🍦

1、[去官网下载客户端](https://github.com/Molunerfinn/PicGo/releases)

2、下载完后安装配置，配置图如下：

![](https://cdn.jsdelivr.net/gh/Cloud300/Picture-bed/blog_pic/PicGO.png#pic_left)

3、总共就这几个步骤，很简单：

- **设定仓库名**：用户名/仓库，就是路径嘛，看你想把上传的图片放到哪个路径下面了

![](https://cdn.jsdelivr.net/gh/Cloud300/Picture-bed/blog_pic/pic_bed1.png#pic_left)

- 设定分支名：**master**

- 设定**Token**：把刚才复制的**Token**粘贴过来

- 设定存储路径：在仓库下面要不要再新建文件夹，最好是建一个，哪有直接把东西放到根目录下的🥳

- 设定自定义域名格式：**https://cdn.jsdelivr.net/gh/ 设定仓库名**，没错就是上面第一项的设定仓库名🚚

- 上面几步设定完之后保存，然后拖一张图片进去，基本不会有什么问题。如果提示**上传失败**，可以看看是不是网络的问题，在国内访问**Github**速度会比较慢，我会用**Steam++加速**，开启这个时候就会上传失败☄☄

  ![](https://cdn.jsdelivr.net/gh/Cloud300/Picture-bed/blog_pic/PicGo_success.png#pic_left)

  

这个方法太简单了，下面的内容是第一次写的，可以忽略掉了，效率最重要🚒🚒<br>

## 如何使用🤔🤔

首先在 Github 上新建一个仓库，命名为CDN，新建这个仓库的目的是用来存放一些大文件（不可超过20M）。

然后在电脑上选择一个地方新建一文件夹，作为本地站点，进入文件夹，打开**git** 终端，在里面输入：

```javascript
git init    ---  初始化
git remote add origin 新建的仓库地址链接（http 或 ssh）
git pull origin master   ---  将远程仓库拉取到本地文件夹
```

上面的命令是在 **origin** 的后面加上你刚才新建的仓库链接，如下：

![](https://cdn.jsdelivr.net/gh/Cloud300/Picture-bed/blog_pic/CDN链接.jpg)<br><br>

你就可以把需要加速的资源放到这个文件夹下（可以多目录）

![](https://cdn.jsdelivr.net/gh/Cloud300/Picture-bed/blog_pic/示例01.jpg)
<br>

我先考进去一个文件测试一下

先执行这几个命令：

```js
git add .   ---  后边这个 . 表示所有
git commit -m '这个引号里填写文件介绍'
git push origin master   ---  将本地站点的文件推送到远程的仓库
```


刷新一下网页，看看有没有：

![](https://cdn.jsdelivr.net/gh/Cloud300/Picture-bed/blog_pic/示例02.jpg)
<br>
好了，到目前为止已经大功告成了，接着我们在博客中直接引用资源即

## 通过  Jsdelivr  引用资源😺

使用方法：

```
https://cdn.jsdelivr.net/gh/你的用户名/你的仓库名/文件路径
```

前半部分的地址是必须要写的，后面跟上你的 **Github** 用户名，接着刚才新建的仓库名，最后就是你要引用的资源路径。

如果你还设有版本号就要这样写（非必须，只是为了区分新旧文件）：

```
https://cdn.jsdelivr.net/gh/你的用户名/你的仓库名@发布的版本号/文件路径
```

看一下我刚上传的这张照片：

![](https://cdn.jsdelivr.net/gh/cloud300/CDN/海边.jpg)
<br>

如果以后需要向CDN仓库里添加或修改文件，首先把文件放到本地仓库，然后一次在本地站点文件夹位置执行以下命令：

```javascript
git pull origin master   ---  拉取远程仓库到本地
git add .
git commit -m '文件描述'
git push origin master
```

上传完成后引用链接即可

写完上面这几条命令，我突然发现，其实一条命令都不要。我们需要上传什么文件直接拖到 **Github** 就可以了:rofl::rofl:

大家根据个人情况来吧

参考链接：[yafine-blog](https://yafine-blog.cn/posts/ee35.html)