## 序
当我用md写文章后，发现缺乏一个整理类的东西，也就是目录，因为当你抛弃有道云后，目录和搜索这些东西就会消失  
我已经确定了我的主战场是vscode+md，所以急缺目录和搜索功能  

我注意到docsify挺精美的，我可以根据某个主题，比如写书笔记做一篇然后持续更新  
它的侧边栏目录和全文搜索是我很喜欢的  

![](https://cdn.jsdelivr.net/gh/mask2012/imgBed/newToDocsify20200115144651.png)



官网在此  
https://docsify.js.org/


## 安装和配置docsify

### 安装 docsify-cli（命令行界面）：  
```
cnpm i docsify-cli -g
```  
npm太慢，换cnpm速度杠杠的
安装完后就可以使用docsify命令了



### 初始化项目
在你想要创建的docsify的地方init一下
```
docsify init ./docs
```
就会在docs目录里生成index.html，**之后的所有配置都会围绕index.html展开**

### 在浏览器中预览
```
docsify serve docs
```


### 侧边栏的配置和生成
刚刚初始化后，默认是没有侧边栏的，默认会读取README.md   
要想有侧边栏，需要在index.html里配置 ```loadSidebar: true,```  
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
```
<script src="//unpkg.com/docsify/lib/plugins/search.min.js"></script>
```
然后配置如下
```
search: {
    maxAge: 86400000, // Expiration time, the default one day
    paths: ['/'], // or 'auto'
    placeholder: '全文搜索',
    noData: '找不到结果',
    depth: 2,
    hideOtherSidebarContent: true, // whether or not to hide other sidebar content
},
```
### emoji
对于emoji文档里没有跳详细说明，所以需要自己测试一下
https://docsify.js.org/#/plugins?id=emoji  
```
<script src="//unpkg.com/docsify/lib/plugins/emoji.min.js"></script>
```

### 图标
在[https://fontawesome.com](https://fontawesome.com)注册后，会给你分配一段引用的脚本，放到index.html里就行了
```
<script src="https://kit.fontawesome.com/8d6d5e7a06.js" crossorigin="anonymous"></script>
```

然后去这里看，觉得哪个图标好，就可以拿过来用  
https://fontawesome.com/icons?d=gallery&m=free  
```
<i class="fab fa-accessible-icon  fa-7x"></i>  
<i class="fab fa-bitcoin fa-3x" style="color:#f00"></i>  
<i class="fas fa-hat-wizard fa-1x" style="color:#f00"></i> 
```
除了网站给出的信息`fas fa-hat-wizard`外，还可以通过fa-1x fa-2x 调整大小，一共有1，2，3，5，7，9这么几个级别  
如果要换颜色可以这样  `style="color:#f00"`  
<i class="fab fa-accessible-icon  fa-7x"></i>  
<i class="fab fa-bitcoin fa-3x" style="color:#097912"></i>  
<i class="fas fa-hat-wizard fa-1x" style="color:#520970"></i>  

### Footer
```
plugins: [
    function (hook) {
        var footer = [
            '<footer>',
            '<span><a href="https://github.com/mask2012">mask2012</a> &copy;2020.</span>',
            '<span>Proudly published with <a href="https://github.com/docsifyjs/docsify" target="_blank">docsify</a>.</span>',
            '</footer>'
        ].join('');

        hook.afterEach(function (html) {
            return html + footer;
        });
    }
]
```


### Tabs
https://jhildenbiddle.github.io/docsify-tabs/#/?id=installation

















