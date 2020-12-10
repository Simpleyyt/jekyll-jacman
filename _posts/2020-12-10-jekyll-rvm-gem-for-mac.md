---
layout: post
title: Jekyll、RVM安装，Gem升级 for Mac
typora-copy-images-to: upload
tags:
- Jekyll
- Mac
categories: Mac
description: 安装Jekyll、RVM、Gem会遇到些问题，在此记录一下。

---

安装Jekyll、RVM、Gem会遇到了各种问题，折腾了一会儿，终于安装好了！！！

[参考链接](https://www.dazhuanlan.com/2019/10/21/5dad89218055f/)

### 0.查看是否安装了gem

```
gem -v
```

<img src="https://wx4.sinaimg.cn/mw690/bc83ecb9gy1glipjhef1qj20vo046q5e.jpg" style="zoom:80%;display:block;margin:auto" alt="" />

`gem update --system`gem更新

### 1.通过gem安装jekyll

```
gem install jekyll
```

<img src="https://wx2.sinaimg.cn/mw690/bc83ecb9gy1glipgid17dj20oo02kabb.jpg" style="zoom:80%;display:block;margin:auto" alt="" />

<img src="https://wx3.sinaimg.cn/mw690/bc83ecb9gy1glipiyisa5j20s2020t9u.jpg" style="zoom:80%;display:block;margin:auto" alt="" />

Ruby版本有问题，需要升级Ruby。

### 2.Ruby升级

[Ruby升级参考链接](https://jingyan.baidu.com/article/948f5924f0fd43d80ff5f9b7.html)

1）安装RVM

```
curl -L get.rvm.io | bash -s stable
```

<img src="https://wx4.sinaimg.cn/mw690/bc83ecb9gy1glipjcv003j20wq0j0gxo.jpg" style="zoom:80%;display:block;margin:auto" alt="" />

国外网站，所以速度比较慢，一次不行可以多试几次。

2）配置环境变量

```
source ~/.profile #修改了环境变量
```

`rvm -v`查询rvm版本信息

<img src="https://wx3.sinaimg.cn/mw690/bc83ecb9gy1glipjlccuqj20wu03idhv.jpg" style="zoom:80%;display:block;margin:auto" alt="" />

3）查询支持的ruby版本信息

<img src="https://wx3.sinaimg.cn/mw690/bc83ecb9gy1glipj704m3j20wq0ggdmk.jpg" style="zoom:80%;display:block;margin:auto" alt="" />

4）指定版本安装

```
rvm install ruby-2.6.1
```

<img src="https://wx3.sinaimg.cn/mw690/bc83ecb9gy1glipk87y92j20x406iq73.jpg" style="zoom:80%;display:block;margin:auto" alt="" />

国外镜像下载太慢了，添加国内镜像

`echo "ruby_url=https://cache.ruby-china.com/pub/ruby" > /Users/tangaihui/.rvm/user/db
`

`gem source -l`查看gem默认

下载镜像

```
gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/
```

ps:默认的镜像：https://rubygems.org/ 记得改回去

5）尝试安装
`
rvm install ruby-2.5.7
`
<img src="https://wx4.sinaimg.cn/mw690/bc83ecb9gy1glipkmtb19j20ws0rk7m4.jpg" style="zoom:80%;display:block;margin:auto" alt="" />

5）查看安装版本信息
`
ruby -v
`
<img src="https://wx3.sinaimg.cn/mw690/bc83ecb9gy1glipgqw44fj20o401yjsg.jpg" style="zoom:80%;display:block;margin:auto" alt="" />

### 3.再次安装
jekyll<img src="https://wx1.sinaimg.cn/mw690/bc83ecb9gy1glipkbw3xjj20lu04w0uu.jpg" style="zoom:80%;display:block;margin:auto" alt="" />

查看版本信息
<img src="https://wx2.sinaimg.cn/mw690/bc83ecb9gy1glipkf41jnj20ie026gmc.jpg" style="zoom:80%;display:block;margin:auto" alt=""/>

### 4.使用jekyll
（1）在～目录下，创建博客相关文件，名如myblog
`
jekyll new myblog
`
<img src="https://wx3.sinaimg.cn/mw690/bc83ecb9gy1glipgmpflgj21160f4dsg.jpg" style="zoom:80%;display:block;margin:auto" alt="" />
ps:这里我多建了一个myblog文件夹，其实不用。

（2）进入jekyll创建的博客文件夹,`jekyll serve`开启jekyll服务，自动创建博客。
<img src="https://wx3.sinaimg.cn/mw690/bc83ecb9gy1glipfyv4hqj20pq08yq7y.jpg" style="zoom:80%;display:block;margin:auto" alt="" />

（3）通过 localhost:4000访问，或者127.0.0.1:4000访问。
<img src="https://wx4.sinaimg.cn/mw690/bc83ecb9gy1glipge55b6j20h00fgdgn.jpg" style="zoom:80%;display:block;margin:auto" alt="" />

