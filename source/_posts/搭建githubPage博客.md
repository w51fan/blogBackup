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

多PC共同管理同一个站点
有时候，我们可能会在多台PC共同管理我们的博客，比如公司电脑和家用电脑。但是使用hexo d部署blog时，会直接将原始的hexo代码转换生成静态的页面，并上传至master分支，这样一来，
我们便无法在另一台电脑获得原始的代码再进行新文章发布。所以，我们需要新建一个hexo分支，来管理我们原始的hexo代码。

$ git checkout -b hexo
Switched to a new branch "hexo"

$ git add .
$ git commit -m "issue"
$ git push origin hexo

这个时候，我们就已经将原始代码push到远程的hexo分支啦～
在另一台电脑下，将hexo分支的代码clone下来

$ git clone -b hexo <remote_repo>

使用hexo（确保电脑已安装hexo-cli），注意这里不需要再hexo init了，不然会覆盖掉之前的配置。

$ cd yourname.github.io
$ npm install
...
$ hexo s

这样一来就可以实现多PC共同管理一个站点了～～
