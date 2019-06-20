---
title: Hexo+Github Page 创建个人博客
date: 2019-04-28 23:11:45
tags: Hexo Github Node.js Git 
cover: /img/1.jpg
categories: HEXO博客
---
#### 准备前工作(Windows环境)

> 安装 node.js
> 安装  git 客户端
> 准备一个 前端开发工具，我这里推荐使用 Hbuilder 或是 Sublime Text，当然你还可以使用git bash 的命令行工具
- [x] **安装node.js、git  请自行百度**
 
---


#### 一切准备就绪，开始...

第一步：安装 ``hexo``

```bash
$ npm install hexo-cli -g
$ hexo init blog
$ cd blog
$ hexo install
$ hexo s
```

第二步：配置SSH Key
> 如果你已创建 GitHub 账号并添加一个远程仓库

那么接下来就要检查本地是否有 SSH key

```bash
$ cd ~/.ssh
$ ls
#进入 .ssh 文件夹，第二步是显示 .ssh 文件下的文件夹及文件。如果 SSH key 存在，就会显示 id_rsa、id_rsa.pub、know_hosts 三个文件 。
```
如果没有也没关系，下面我们就来创建 SSH key
```bash
$ ssh-keygen -t rsa -C "你的邮箱"  #注意"你的邮箱"应该是配置git时的邮箱
```

把 "你的邮箱" 替换成你真实的邮箱，然后点击回车。接着会让你输入文件名，点击回车直接忽略，接着会让输入两次密码，点击两次回车，直接设置为空，不用输入密码 。

创建成功后，可以通过如下命令拷贝 SSH key 的内容 ：
```bash
$ clip < ~/.ssh/id_rsa.pub"
```

现在已拷贝了 SSH key 的内容，那么 GitHub 如何添加 SSH key 呢 ？
进入你的GitHub首页，点击setting 然后在左侧找到SSH and GPG keys ，点击New SSH key将刚才复制的内容粘贴到key中，title随意


第三步：编辑站点目录下的`_config.yml`文件

```yml
# 添加下列参数

deploy:
  type: git
  repo: git@github.com:leitianjin/leitianjin.github.io.git #这里要配置自己的代码仓库哦，否则上传不到你github仓库
  branch: master
```

第四步：打包上传

完成上面步骤后，接着就可以打包上传了

```bash
# 执行hexo 命令  注意一定要在站点根目录下执行
 

  $ hexo clean  #其实我也不知道这条命令有卵用，按官方文档操作就好
  $ hexo g      #将.MD 文件及其相关文件转换成html、js、css 静态文件
  $ hexo d		#将生成的静态文件上传到你建立的github 仓库  
  
```





--- 
