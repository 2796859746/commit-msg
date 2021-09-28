\---

title: 关于hexo

top: false

cover: false![logo](C:\Users\Administrator\Desktop\logo.png)

toc: true

mathjax: tC:\Users\Administrator\Desktop\blog\source\_posts\1.pngrue

date: 2021-09-18 12:37:36

password:

summary:

tags:

categories:

\---



\## 一、了解 hexo



\### 1.1 什么是 hexo？



hexo 是使用 nodejs 开发的一个快速、简洁、高效、开源的静态博客生成器。



\### 1.2 hexo 如何解析文章？



hexo 使用 Markdown 解析文章，因此，文章需采用 Markdown 语法编写，在几秒内，即可利用靓丽的主题生成静态网页。类似于 jekyll、Octopress、Wordpress，我们可以用 hexo 创建自己的博客，托管到 github，绑定自己的域名。



\## 二、选择 hexo 的理由



市场上也有不少其他类似 hexo 的博客生成器，为什么选择 hexo 呢？



\- 非常小巧，使用 nodejs 开发，下载安装时只需要几个简答的 npm 命令即可



\- 纯静态博客，不需要额外的数据库、php 环境…仅仅需要一个 nodejs 环境即可



\- 由于是静态博客，所以，可以非常方便部署到 github



\- 支持 markdown 语法、兼容 windows linux mac，高可扩展性和自定义，而且有非常多的 hexo 主题



\## 三、安装 hexo



这里我们针对 windows 环境进行演示说明，其他环境大体上与此一致，详细请参照[官方文档](https://hexo.io/zh-cn/docs/index.html)。



在安装 hexo 之前，你需要保证环境中有 Node.js 和 Git 环境，这里我们就不赘述他们俩的安装。



在 Node.js 和 Git 安装无误情况下，执行：



\```bash

$ npm install -g hexo-cli

\```



通过 npm 进行 hexo 的全局安装，这么简单，一条命令 hexo 即安装完成。



\## 四、hexo 使用



\### 4.1 建站



安装 hexo 完成后，就可以进行使用了。



首先，对于不是从 github 更新的 hexo 库，我们需要自己初始化本地 hexo 库：



\```bash

$ hexo init <folder>

$ cd <folder>

$ npm install

\```



\### 4.2 结构说明



\#### 4.2.1 \_config.yml



网站的[配置](https://hexo.io/docs/configuration.html)信息，可以在此配置大部分的参数。



\#### 4.2.2 package.json



应用程序的信息。EJS, Stylus 和 Markdown renderer 已默认安装，你可以自由移除。



*> package.json*

*> {*

*> "name": "hexo-site",*

*> "version": "0.0.0",*

*> "private": true,*

*> "hexo": {*

*> "version": ""*

*> },*

*> "dependencies": {*

*> "hexo": "^3.0.0",*

*> "hexo-generator-archive": "^0.1.0",*

*> "hexo-generator-category": "^0.1.0",*

*> "hexo-generator-index": "^0.1.0",*

*> "hexo-generator-tag": "^0.1.0",*

*> "hexo-renderer-ejs": "^0.1.0",*

*> "hexo-renderer-stylus": "^0.2.0",*

*> "hexo-renderer-marked": "^0.2.4",*

*> "hexo-server": "^0.1.2"*

*> }*

*> }*



\#### 4.2.3 scaffolds



模版 文件夹。当你新建文章时，Hexo 会根据 scaffold 来建立文件。



\#### 4.2.4 source



资源文件夹是存放用户资源(blog)的地方。



\#### 4.2.5 public



Markdown 和 HTML 文件会被解析并放到 public 文件夹，而其他文件会被拷贝过去。



\#### 4.2.6 themes



主题文件夹。Hexo 会根据主题来生成静态页面。



这样即建站成功。



\### 4.3 写作



\```bash

$ hexo new [layout] <title>

\```



这条命令用来创建一篇新文章，用 hexo new 创建的文章格式是 md，和普通 markdown 文档不一样，它包含了当前 layout 提供的头部模板，如 post layout 布局的文章，顶部会出现：



*> — —*

*> title: Hexo 介绍及常用安装使用*

*> date: 2016-11-27 21:59:22*

*> tags: hexo*

*> — —*



在\_config.yml 中会有 default_layout 这个参数，默认是 post，也就是说不加 layout 参数时，new 出来的文章使用 post 布局。当然，default_layout 可以根据自己的需要进行更改。

Hexo 有三种默认布局：post、page 和 draft，它们分别对应不同的路径，而你自定义的其他布局和 post 相同，都将储存到 source/\_posts 文件夹。



\#### 4.3.1 layout



Hexo 有三种默认布局：post、page 和 draft，它们分别对应不同的路径，而你自定义的其他布局和 post 相同，都将储存到 source/\_posts 文件夹。



| 布局 |   路径    |

| :---: | :-------------: |

| post | source/\_posts |

| page |   source   |

| draft | source/\_drafts |



\#### 4.3.2 文件名称



Hexo 默认以标题做为文件名称，但你可以编辑\_config.yml 中的 new_post_name 参数来改变默认的文件名称，举例来说，设为 :year-:month-:day-:title.md 可让您更方便的通过日期来管理文章。



|  变量  |        描述        |

| :------: | :--------------------------------: |

| :title | 标题（小写，空格将会被替换为短杠） |

| :year  |   建立的年份，比如， 2016    |

| :month | 建立的月份（有前导零），比如， 04 |

| :i_month | 建立的月份（无前导零），比如， 4 |

|  :day  | 建立的日期（有前导零），比如， 07 |

| :i_day | 建立的日期（无前导零），比如， 7 |



文件创建成功，剩下的就是用 markdown 语法进行愉快的创作了！



![1](C:\Users\Administrator\Desktop\1.png)