## 序
当我用md写文章后，发现缺乏一个整理类的东西，也就是目录，因为当你抛弃有道云后，目录和搜索这些东西就会消失  
我已经确定了我的主战场是vscode+md，所以急缺目录和搜索功能  

我注意到docsify挺精美的，我可以根据某个主题，比如写书笔记做一篇然后持续更新  
它的侧边栏目录和全文搜索是我很喜欢的  

![](https://cdn.jsdelivr.net/gh/mask2012/imgBed/newToDocsify20200115144651.png)

官网在此  
https://docsify.js.org/


## 安装和配置docsify
### 首先安装 docsify-cli（命令行界面）：  
```
cnpm i docsify-cli -g
```  
npm太慢，换cnpm速度杠杠的

### 初始化项目
在你想要创建的docsify的地方init一下，如果带目录就在目录里创建，如果不带就在当前目录创建
```
docsify init ./docs
```
创建完成会在目录里生成index.html，之后的配置都会围绕index.html展开

### 侧边栏的配置和生成
刚刚初始化后，默认是没有侧边栏的，默认会读取README.md   
要想有侧边栏，需要在index.html里配置配置 ```loadSidebar: true,```  
那么它就会去找_sidebar.md这个文件  
这属于潜规则  
如果你不喜欢这个潜规则，可以指定地址比如 ```loadSidebar: 'summary.md'``` 
```
window.$docsify = {
    name: '',
    repo: '',
    loadSidebar: true,
}
```

侧边栏里的内容不是自动生成的，需要手写，就和写md的链接一样，为了效率我会让文件名全部保持一致
```
* [用docsify整理目录1.md](用docsify整理目录1.md)
* [用docsify整理目录2.md](用docsify整理目录2.md)
* [用docsify整理目录3.md](用docsify整理目录3.md)
```

### 搜索
搜索首先引用地址
<script src="//unpkg.com/docsify/lib/plugins/search.min.js"></script>









