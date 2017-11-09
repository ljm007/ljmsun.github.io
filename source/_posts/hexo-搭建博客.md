---
title: hexo GitHub搭建个人博客的全教程
date: 2017-11-09 16:20:15
tags:
 - hexo
---
Hexo 是一个快速、简洁且高效的博客框架。Hexo使用Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

GitHub这个全球最大的同性交友网站，提供Pages服务，是一个免费的静态网页托管服务。so我们可以利用这个搭建自己的个人博客，现在哥带大家一起飞。。。。。。。。。

## 我们先来配置环境
>*  安装git
下载地址：[http://git-scm.com/download/](http://git-scm.com/download/)
下载完成后一路next,git的配置我就不说了，大家应该都会
>* 安装Node.js
下载地址：[https://nodejs.org/en/download/](https://nodejs.org/en/download/)
也是一路next，具体的安装可以参考[安装Node.js](http://www.w3cschool.cc/nodejs/nodejs-install-setup.html)
>* 现在就可以安装hexo了
打开命令行，可以用win的cmd也可以用gitbash，这里用gitbash演示。

## hexo的安装跟配置
有句话说的好“万里长城不倒，一支红杏出墙来”，所以我们用npm安装hexo会很慢还不稳定，使用淘宝提供的镜像cnpm就不错。
但来回切换npm源比较麻烦，所以我们先安装nrm来管理npm源的切换。
##### 安装nrm(切换npm源的利器)
```
npm install -g nrm --registry=https://registry.npm.taobao.org
```
##### 切换npm源到cnpm
```
nrm use cnpm
```
##### 安装 hexo
```
npm install -g hexo
```
现在创建一个文件夹,如blog,里面存放hexo的配置文件，cd到这个文件夹里
执行命令初始化hexo
```
hexo init
```
生成静态页面
```
hexo g
```
启动本地服务，预览网页
```
hexo server
```
在浏览器中打开http://localhost:4000就可以看到
## 现在配置Github
新建一个项目，选择New repository

![](/images/github_new.png)

在Repository name下填写yourname.github.io，比如我的就是ljmsun.github.io

![](/images/github_name.png)

接着就是开启pages服务，点击项目界面的setting页面找到GitHub pages，开启

![](/images/github_setting.png)
![](/images/github_pages.jpg)

## 部署到GitHub
>* 先把自己的git密钥添加到GitHub上

![](/images/github_ssh.png)

>* 修改hexo的配置
找到_config.yml文件，按如下修改：
```
deploy:
  type: git
  repo: git@github.com:yourname/yourname.github.io.git
  branch: master
```
![](/images/hexo_config.png)

>* 安装git的部署插件
```
npm install hexo-deployer-git --save
```
## 写个博客test一下
```
hexo new "test" //新建个博客
hexo g          //生成静态页面
hexo d          //部署
```

至此，你的个人博客就已经搭建完成了，输入https://yourName.github.io 就可以看到新鲜热乎的博客了












