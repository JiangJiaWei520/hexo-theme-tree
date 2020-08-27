## Hexo 主题 Tree

一个简洁的主题，主要功能是 “树状导航” + “树状目录”，可选配“评论”和“阅读量”功能。

有问题欢迎及时联系，issues、邮件都行

Demo：[https://wujun234.github.io/](https://wujun234.github.io/)

![](source/Tree.png)

## 使用说明

### 1 下载主题

下载主题到 `hexo` 根目录中 `themes` 目录下
```
git clone https://github.com/wujun234/hexo-theme-tree.git  themes/tree
```

修改 `hexo` 根目录的 `_config.yml`
```
theme: tree
```
### 2 配置主题

如果要使用 `valine` 的评论及阅读量功能，需要在 `themes/tree` 路径下的 `_config.yml` 文件中，填写自己申请的 `leancloud` 账户下面的 `appID` 和 `appKey`

```
valine:
    appID: 
    appKey: 
```

若不需使用，则设置
```
valine:
    enableComment: false 
    enableCounter: false
```

### 3 导航栏和图标(没有配置化，需要写死)
- 导航栏：当前没有配置化，需要修改`themes/tree/layout/_partial` 路径下的 `header.ejs` 文件
- 图标：替换`themes/tree/source` 路径下的`favicon.ico` 文件

- -about：

  ```
  <li class="menu-item">
  <a href="https://jiangjiawei520.github.io/hexo_notes.github.io/about/index.html" class="menu-item-link">ABOUT</a>
  </li>
  ```

  

### 4 about 页
在 `source`路径下，与`_posts`文件夹平行，建立一个`about`页

执行
```
hexo new page --path about/index "About"
```
参考：https://hexo.io/zh-cn/docs/commands.html#new

### 5 文章树、目录树
页面左侧的文章树是根据 source 文件夹里的文章和文件夹生成的，目录树是根据文章中的标题生成的

## 其他
###  推荐插件

推荐安装 [Markdown-it](https://github.com/markdown-it/markdown-it) 插件渲染 `Markdown`

替换之后注意将 \_config.yml 中 hexo 默认的 Markdown 配置改一下
```
highlight:
  enable: false
  line_number: false
  auto_detect: false
  tab_replace: ''
```

### 访问管理
我自己用的是百度统计 https://tongji.baidu.com ，很简单，注册后在 'head' 里加一个 '<script>' 块就行了
1. 新版统计代码获取

<script>
var _hmt = _hmt || [];
(function() {
  var hm = document.createElement("script");
  hm.src = "https://hm.baidu.com/hm.js?xxxxxxxxxxxxxxxxxx";
  var s = document.getElementsByTagName("script")[0]; 
  s.parentNode.insertBefore(hm, s);
})();
</script>

2. 代码安装说明

      a、请将代码添加到网站全部页面的</head>标签前。

      b、在header.ejs的页头模板页面中安装，以达到一处安装，全站皆有的效果。



 3.检查

您可以用浏览器自带的开发者工具进行手动查看，非常便捷。

> 方法一：用Chrome 浏览器查看代码是否已安装方法：

①打开要检查的网页，右键点击弹出菜单中的审查元素（或直接按F12），打开开发者工具控制台。

②选中控制台上方的Network 按钮，按照页面提示进行操作

③F5 刷新下页面，检查表格中是否有名字是hm.js？的项，若有，则证明已安装百度统计代码。若无，则证明未安装。

④进阶：如果有hm.js 项（或者h.js，hm.js 表示异步代码，h.js表示访问分析代码），但在百度统计里看不到网站数据（pv等），则有可能是装错了代码。需要检查是否装对代码。

