title: 搭建githubPage博客
date: 2020-01-19 14:37:17
---
用原生的方法来管理博文十分的不便，因此便有了Hexo Admin这一插件来方便我们的操作。
首先，安装插件。

npm install --save hexo-admin

启动服务器。

hexo server -d

即可在localhost:4000/admin/中编辑博文了。


![upload successful](\images\pasted-0.png)

然后，Deploy之前，还需要编辑配置文件_config.yml。(否则会出现Error: Config value "admin.deployCommand" not found或者Error: spawn hexo ENOENT之类的报错。)
如果是Windows则在末尾加上

admin:
  deployCommand:'hexo-pubish.bat'

![upload successful](\images\pasted-3.png)
然后在同级目录新建hexo-pubish.bat文件，文件内容如下：

hexo g -d

PS：关于Hexo Admin插入图片
Hexo Admin可以直接复制图片粘贴，然后自动下载到source/images目录并重命名。但在Windows中粘贴后会出现裂图。这时就需要手动把括号中的前后两个斜杠去掉，就能正常显示。

没有去掉

![upload successful](\images\pasted-1.png)

去掉之后

![upload successful](\images\pasted-2.png)

