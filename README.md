#使用Jekyll在Github上面搭建blog
这个blog只是自己在的一个尝试，个人主页github主页请移步
[runke github](http://runkingzhang.github.io/)

创建项目
1.在本地创建blog
2.本地初始化
git init
3.创建设置文件。
新建_config.yml
内容为：
　baseurl: /jekyll_demo
 4.新建布局文件夹
 _layouts
在_layouts下面创建文件
 default.html
default.html的内容如下：
```html
<!DOCTYPE html>
　　<html>
　　<head>
　　　　<meta http-equiv="content-type" content="text/html; charset=utf-8" />
　　　　<title>{{ page.title }}</title>
　　</head>
　　<body>

　　　　{{ content }}

　　</body>
　　</html>
```
5.新建提交文件
创建文件夹：_posts
新建文件：2012-08-25-hello-world.html
内容如下：
```html
---
　　layout: default
　　title: 你好，世界
---
　　<h2>{{ page.title }}</h2>
　　<p>我的第一篇文章</p>
　　<p>{{ page.date | date_to_string }}</p>
```

6.创建首页
在根目录下面创建index.html
代码内容如下：
```html
---
　　layout: default
　　title: 我的Blog
---
　　<h2>{{ page.title }}</h2>
　　<p>最新文章</p>
　　<ul>
　　　　{% for post in site.posts %}
　　　　　　<li>{{ post.date | date_to_string }} <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
　　　　{% endfor %}
　　</ul>
```
7.发布内容
在github上面新建rep叫做blog
```dos　　
git add .
git commit -m "first post"
git remote add blog https://github.com/username/jekyll_demo.git
git push blog gh-pages
```

8.访问
[http://runkingzhang.github.com/blog](http://runkingzhang.github.com/blog)
就可以看到对应blog内容。

9.现在还用的比较常见的方式就是在github上面使用issues来建立对应的blog，这样这边不但
支持markdown，还可以让别的用户来留言,不需要上传文件，也方便修改。相对来说这种方式是最好的。
[github issues ](https://github.com/runkingzhang/runkingzhang.github.com/issues?state=open)


