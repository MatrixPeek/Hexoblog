title: Hexo重部署
date: 2015-4-12
categories: Hexo
---


本地文件夹Hexo丢失了，找不回来，怕你啊，大不了全部重新配置一遍！

##开始重新配置
首先git bash，输入命令
``` bash
npm install -g hexo
```
但是安装失败，显示
``` bash
npm WARN optional dep failed,continuing fsevents@0.3.5
```
解决方法：卸载node.js并且重新安装
安装好后执行
``` bash
npm install -g hexo
```
建立文件夹Hexo,右键git bash here,输入
``` bash
npm install
```


##git配置
```bash
hexo g 
```
配置失效，显示
``` bash
ERROR:not found:github
```
解决方案：deploy的type的github改为git,且输入命令
``` bash
npm install hexo-deployer-git --save
```


##hexo优化

###更改favicon
favicon.ico在Hexo\themes\jacman\source\img路径中，可使用[this page](http://www.faviconer.com/ "Title")这个网站在线制作favicon，也可以使用[this page](http://lvwenhan.com/convertico/ "Title")在线将.jpg或.png格式的图片转化为.ico格式的图片
###更改网站logo
将你喜欢的图片大小更改为64x64和128x128，保存在Hexo\themes\jacman\source\img路径即可


##hexo的使用
###Hexo发表新文章
方法一：在Hexo文件夹Git Bash
``` bash
$ hexo n #写文章
```
执行命令后会在项目\source_posts中生成my new post.md文件，用编辑器打开编写即可
方法二：直接在\source_posts中新建一个md文件，编写

###本地预览
``` bash
$ hexo g #生成
$ hexo s #本地预览
```
也可使用合并命令
``` cbash
$ hexo s -g
```

###推送到服务器
``` bash
$ hexo g #生成
$ hexo d #部署
```
也可使用合并命令
``` bash
$ hexo d -g
```

###发表文章的Markdown语法
使用jacman或pacman主题，建议按此标准语法写
```
	title: postName #文章页面上的显示名称，可以任意修改，不会出现在URL中
	date: 2013-12-02 15:30:16 #文章生成时间，一般不改，当然也可以任意修改
	categories: example #分类
	tags: [tag1,tag2,tag3] #文章标签，可空，多标签请用格式，注意:后面有个空格
	description: 附加一段文章摘要，字数最好在140字以内。
	---

	以下正文
```


