# **docsify快速上手体验**
做一个博客除了可以使用现在各个博客网站，还可以自行DIY一个。每种方法都有自己的优劣点。如：
Gitbook访问速度慢；博客网站，历史编辑除了草稿箱外，没有太多的历史信息，偶然发现docsify。
本地编辑md，利用Github做版本控制和多人协作，最后使用Github Pages进行发布预览。大家可以方便沟通、交流、改进。

# docsify是什么
docsify是一个文档站点的生成器。可以直接读取本地md文件，进行渲染。


# 怎么用？

安装，初始化，启动三连击。

1、使用node全局安装:

` npm i docsify-cli -g`

2、使用如下命令初始化，至于名称为docs是为了让github可以直接读取生成网站的默认目录

`
docsify init ./docs
`
生成文件：index.html 入口，README.MD 主页 ，.nojekyll 阻止github pages 忽略以下划线开头文件

3、启动

`
docsify serve
`

## 路由说明

正如很多的 web框架一样，所有的释放的自由，必须按照它的规则，访问自然有自己的一套规则 

``` 
docs/README.md  -->http://demo.com
docs/first.md   -->http://demo.com/first
docs/second/README.md  -->http://demo.com/second/
docs/second/guide.md  -->http://demo.com/second/guide
``` 

## 导航

其实将index.html暴露出来，可以自己使用html的标签进行实现。当然省事还是使用docsify的方式进行进行加载。

修改docsify的对象：

``` 
<script>
  window.$docsify = {
    loadNavbar: true
  }
</script>
<script src="//unpkg.com/docsify"></script>
``` 

当然再navbar中添加一个_navbar.md文件，使用如下的方式进行创建。



## 侧边栏
使用docsify的功能开启侧边栏
``` js
<script>
  window.$docsify = {
    loadSidebar: true
  }
</script>
<script src="//unpkg.com/docsify"></script>

```


## 部署

在对应得仓的setting中的github pages进行设置，src-->master branch/docs folder

## 插件
1、搜索插件
在index.html添加如下资源文件

`<script src="//unpkg.com/docsify/lib/plugins/search.js"></script>`

2、代码插件
在index.html引入如下资源文件，同时需要在应用的地方，使用``` 进行代码块的编写
```
  <script src="//unpkg.com/docsify-copy-code"></script>
  <script src="//unpkg.com/prismjs/components/prism-bash.js"></script>
  <script src="//unpkg.com/prismjs/components/prism-php.js"></script>
  <script src="//unpkg.com/prismjs/components/prism-python.js"></script>
```


# 更多资料

https://docsify.js.org/#/
