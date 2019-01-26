---
title: hexo使用本地图片
date: 2019-01-25 20:10:09
tags:
---

## 1、修改配置文件_config.yml

``` 
_config.yml 里Writing -- post_asset_folder:true

``` 
## 2、安装一个可以上传本地图片的插件
``` 
npm install hexo-asset-image --save

``` 

## 3、运行hexo n "xxxx"

/source/_posts文件夹内除了xxxx.md文件还有一个同名的文件夹

## 4、引用图片

``` 
最后在xxxx.md中想引入图片时，先把图片复制到xxxx这个文件夹中，
然后只需要在xxxx.md中按照markdown的格式引入图片：

![你想输入的替代文字](xxxx/图片名.jpg)

注意： xxxx是这个md文件的名字，也是同名文件夹的名字。
只需要有文件夹名字即可，不需要有什么绝对路径。
你想引入的图片就只需要放入xxxx这个文件夹内就好了，很像引用相对路径。

``` 

## 5、其他

``` 
hexo g生成页面后，进入public\2017\02\26\index.html文件中查看相关字段，
可以发现，html标签内的语句是<img src="2017/02/26/xxxx/图片名.jpg">，
而不是<img src="xxxx/图片名.jpg>。
这很重要，关乎你的网页是否可以真正加载你想插入的图片。

``` 

