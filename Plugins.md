# GitBook 插件
<!--email_off-->  
记录一些实用的插件, 如果要指定插件的版本可以使用 `plugin@0.3.1`。下面的插件在 GitBook 的 `3.2.3` 版本中可以正常工作，因为一些插件可能不会随着 GitBook 版本的升级而升级，即下面的插件可能不适用高版本的 GitBook，所以这里指定了 GitBook 的版本。另外本文记录的插件在 Linux 下都是可以正确工作的，windows 系统没有测试。这里只是列举了一部分插件，如果有其它的需求，可以到 [插件官网](https://plugins.gitbook.com/) 区搜索相关插件。
<!--/email_off-->


## 1. Klipse

集成 Klipse (online code evaluator)

[插件地址](https://www.npmjs.com/package/gitbook-plugin-klipse)  
[Klipse](https://github.com/viebel/klipse)

```json
{
    "plugins": ["klipse"]
}
```

klipse 目前支持下面的语言：

    * javascript: evaluation is done with the javascript function eval and pretty printing of the result is done with pretty-format
    * clojure[script]: evaluation is done with Self-Hosted Clojurescript
    * ruby: evaluation is done with Opal
    * C++: evaluation is done with JSCPP
    * python: evaluation is done with Skulpt
    * scheme: evaluation is done with BiwasScheme
    * PHP: evaluation is done with Uniter
    * BrainFuck
    * JSX
    * EcmaScript2017
    * Google Charts: See Interactive Business Report with Google Charts.

示例：

###1.1. Clojure & ClojureScript
####1.1.1. For clojure[script] code evaluation:

    ```eval-clojure
    (map inc [1 2 3])
    ```

```eval-clojure
(map inc [1 2 3])
```
####1.1.2. For clojurescript code transpilation:

    ```transpile-cljs
    (map inc [1 2 3])
    ```

```transpile-cljs
(map inc [1 2 3])
```
###1.2. Javascript

    ```eval-js
    [1,2,3].map(function(x) { return x + 1;})
    ```

```eval-js
[1,2,3].map(function(x) { return x + 1;})
```
###1.3. Python

    ```eval-python
    print [x + 1 for x in range(10)]
    ```

```eval-python
print [x + 1 for x in range(10)]
```
###1.4. Ruby

    ```eval-ruby
    [1,2]*10
    ```

```eval-ruby
[1,2]*10
```
###1.5. Scheme

    ```eval-scheme
    (let ((x 23)
          (y 42))
      (+ x y))
    ```

```eval-scheme
(let ((x 23)
      (y 42))
  (+ x y))
```
###1.6. PHP

    ```eval-php
    $var = ["a" => 1];
    var_dump($var);
    ```

```eval-php
$var = ["a" => 1];
var_dump($var);
```

## 2. Prism
使用 `Prism.js` 为语法添加高亮显示，需要将 `highlight` 插件去掉。
该插件自带的主题样式较少，可以再安装 `prism-themes` 插件，里面多提供了几种样式，
具体的样式可以参考 [这里](https://github.com/PrismJS/prism-themes)，在设置样式时要注意设置 css 文件名，而不是样式名。

[Prism 插件地址](https://www.npmjs.com/package/gitbook-plugin-prism)
[prism-themes 插件地址](https://plugins.gitbook.com/plugin/prism-themes)

```json
{
    "plugins": [
        "prism",
        "-highlight"
    ],
    "pluginsConfig": {
        "prism": {
            "css": [
                "prismjs/themes/prism-dark.css"
            ]
        }
    }
}
```

由于其他插件使用代码块概念来表示其他功能，您可以忽略某些语言

```json
{
  "pluginsConfig": {
    "prism": {
      "ignore": [
        "mermaid",
        "eval-js"
      ]
    }
  }
}
```

如果需要修改背景色、字体大小等，可以在 `website.css` 定义 `pre[class*="language-"]` 类来修改，下面是一个示例：
```css
pre[class*="language-"] {
    border: none;
    background-color: #f7f7f7;
    font-size: 1em;
    line-height: 1.2em;
}
```

## 3. Sectionx
将页面分块显示，标签的 tag 最好是使用 b 标签，如果使用 h1-h6 可能会和其他插件冲突。  
[插件地址](https://www.npmjs.com/package/gitbook-plugin-sectionx-cn)

    class: the button has to belong to the class "section".
    target: when pressed, the section with the id of target will be toggled.
    show: the text on the button when the target section is hidden.
    hide: the text on the button when the target section is visible.
```json
{
    "plugins": [
       "sectionx"
   ],
    "pluginsConfig": {
        "sectionx": {
          "tag": "b"
        }
      }
}
```
使用示例

<!--sec data-title="Sectionx Demo" data-id="section0" data-show=true ces-->

Insert markdown content here (you should start with h3 if you use heading).

<!--endsec-->
<button class="section" target="section0" show="Show next section" hide="Hide next section"></button>

## 4. ancre-navigation
页面右上角悬浮导航以及回到顶部按钮
[插件地址](https://www.npmjs.com/package/gitbook-plugin-ancre-navigation)

```json
{
  "plugins": [
    "ancre-navigation"
  ]
}
```

## 5. Mermaid-gb3
支持渲染[Mermaid](https://github.com/knsv/mermaid)图表  
[插件地址](https://www.npmjs.com/package/gitbook-plugin-mermaid-gb3)
```json
{
  "plugins": [
    "mermaid-gb3"
  ]
}
```
使用示例:
```mermaid
graph TD;
  A-->B;
  A-->C;
  B-->D;
  C-->D;
```

## 6. Sharing-plus
分享当前页面，比默认的 sharing 插件多了一些分享方式。

[插件地址](https://www.npmjs.com/package/gitbook-plugin-sharing-plus)

```json
 {
  "plugins": [
    "-sharing",
    "sharing-plus"
  ]
}
```
配置:

```json
{
  "pluginsConfig": {
    "sharing": {
      "douban": false,
      "facebook": false,
      "google": true,
      "hatenaBookmark": false,
      "instapaper": false,
      "line": true,
      "linkedin": true,
      "messenger": false,
      "pocket": false,
      "qq": false,
      "qzone": true,
      "stumbleupon": false,
      "twitter": false,
      "viber": false,
      "vk": false,
      "weibo": true,
      "whatsapp": false,
      "all": [
        "facebook",
        "google",
        "twitter",
        "weibo",
        "instapaper",
        "linkedin",
        "pocket",
        "stumbleupon"
      ]
    }
  }
}
```

## 7. Search Plus
支持中文搜索, 需要将默认的 `search` 和 `lunr` 插件去掉。

[插件地址](https://www.npmjs.com/package/gitbook-plugin-search-pro)

```json
{
    "plugins": ["-lunr", "-search", "search-plus"]
}
```

## 8. Edit Link
如果将 GitBook 的源文件保存到github或者其他的仓库上，使用该插件可以链接到当前页的源文件上。   
[插件地址](https://www.npmjs.com/package/gitbook-plugin-edit-link)
```json
{
  "plugins": [
    "edit-link"
  ],
  "pluginsConfig": {
    "edit-link": {
      "base": "https://github.com/USER/REPO/edit/BRANCH",
      "label": "Edit This Page"
    }
  }
}
```

## 9. hide-element
Hide the element that you don't want to see.  
[插件地址](https://www.npmjs.com/package/gitbook-plugin-hide-element)
```json
{
  "plugins": [
    "hide-element"
  ],
  "pluginsConfig": {
    "hide-element": {
      "elements": [".gitbook-link"]
    }
  }
}
```

## 10. Anchors
添加 Github 风格的锚点样式

![](https://cloud.githubusercontent.com/assets/2666107/3465465/9fc9a502-0266-11e4-80ca-09a1dad1473e.png)

[插件地址](https://www.npmjs.com/package/gitbook-plugin-anchors)
```json
{
  "plugins": [
    "anchors"
  ]
}
```

## 11. chapter-fold
Extended from the expandable-chapters plugin, and make a little modify. Thx for the original author.
Tiny change to the expandable-chapters plugin from https://github.com/DomainDrivenArchitecture/ to use smaller arrows.

[插件地址](https://www.npmjs.com/package/gitbook-plugin-chapter-fold)
```json
{
  "plugins": ["chapter-fold"]
}
```

## 12. expandable-chapters
这个插件为每一章添加了一个图标，它有一个子列表和 css 状态，用于子列表折叠展开。

[插件地址](https://www.npmjs.com/package/gitbook-plugin-expandable-chapters)
```json
{
  "plugins": ["expandable-chapters"]
}
```

## 13. code
代码块很酷，但也可以更酷。这个插件为多行块添加行号和一个复制按钮来轻松复制块的内容。

[插件地址](https://www.npmjs.com/package/gitbook-plugin-code)
```json
{
  "plugins": ["code"],
  "pluginsConfig": {
    "code": {
      "copyButtons": false
    }
  }
}
```

## 14. insert-logo
以下插件将徽标插入导航栏（摘要上方和搜索输入上方）。
只需将 logo.png 文件拖放到 GitBook 的根文件夹中，然后将此插件添加到您的 book.json 中：

[插件地址](https://www.npmjs.com/package/gitbook-plugin-insert-logo)
```json
{
  "plugins": ["insert-logo"],
  "pluginsConfig": {
    "insert-logo": {
      "url": "http://www.example.com/my-logo.png",
      "style": "background: none;"
    }
  }
}
```

## 15. custom-favicon
将您自己的图标添加到 gitbook 主题。
插件删除位于“_book/gitbook/images/favicon.ico”的 gitbook favicon 并替换为您的 favicon。
可能有更好的方法来做到这一点，但这至少适用于大多数用例。然而，这是一个骇入手段😃

[插件地址](https://www.npmjs.com/package/gitbook-plugin-custom-favicon)
```json
{
  "plugins" : ["custom-favicon"],
  "pluginsConfig" : {
    "favicon": "path/to/favicon.ico"
  }
}
```

## 16. pageview-count
文档页面阅读数插件

[插件地址](https://www.npmjs.com/package/gitbook-plugin-pageview-count)
```json
{
  "plugins": [
    "pageview-count"
  ]
}
```

## 17. Tbfed-pagefooter
为页面添加页脚

[插件地址](https://plugins.gitbook.com/plugin/tbfed-pagefooter)
```json
{
  "plugins": [
    "tbfed-pagefooter"
  ],
  "pluginsConfig": {
    "tbfed-pagefooter": {
      "copyright": "Copyright &copy Skynetcus.com 2021",
      "modify_label": "该文件修订时间：",
      "modify_format": "YYYY-MM-DD HH:mm:ss"
    }
  }
}
```

## 18. Advanced Emoji
支持emoji表情

[emoij表情列表](http://www.emoji-cheat-sheet.com/)  
[插件地址](https://plugins.gitbook.com/plugin/advanced-emoji)

```json
{
  "plugins": [
    "advanced-emoji"
  ]
}
```
使用示例：
:bowtie: :smile: :laughing: :blush: :smiley: :relaxed:

使用忽略标志例如，如果您想要不替换表情符号的出现，您需要将它们包装在以下注释中。

    <!-- ignore:advanced-emoji:start -->
    :white_check_mark:
    <!-- ignore:advanced-emoji:end -->
您甚至可以在代码块或更多行周围设置忽略。
例如：

    <!-- ignore:advanced-emoji:start -->
    '''
    Check the Code
    Code ... :white_check_mark:
    '''
    <!-- ignore:advanced-emoji:end -->

## 19. KaTex
为了支持数学公式, 我们可以使用`KaTex`和`MathJax`插件, 官网上说`Katex`速度要快于`MathJax`

[插件地址](https://www.npmjs.com/package/gitbook-plugin-katex)  
[MathJax使用LaTeX语法编写数学公式教程](http://iori.sinaapp.com/17.html)
```json
{
  "plugins": [
    "katex"
  ]
}
```
使用示例:

When {% math %}a \ne 0{% endmath %}, there are two solutions to {% math %}(ax^2 + bx + c = 0){% endmath %} and they are {% math %}x = {-b \pm \sqrt{b^2-4ac} \over 2a}.{% endmath %}

$$
\int_{-\infty}^\infty g(x) dx
$$

$$
1 \over 3
$$

## 20. Local Video
使用Video.js 播放本地视频  
[插件地址](https://www.npmjs.com/package/gitbook-plugin-local-video)
```json
{
  "plugins": [
    "local-video"
  ]
}
```
使用示例：为了使视频可以自适应，我们指定视频的`width`为100%，并设置宽高比为`16:9`，如下面所示
```
{% raw %}
<video id="my-video" class="video-js" controls preload="auto" width="100%"
poster="https://zhangjikai.com/resource/poster.jpg" data-setup='{"aspectRatio":"16:9"}'>
  <source src="https://zhangjikai.com/resource/demo.mp4" type='video/mp4' >
  <p class="vjs-no-js">
    To view this video please enable JavaScript, and consider upgrading to a web browser that
    <a href="http://videojs.com/html5-video-support/" target="_blank">supports HTML5 video</a>
  </p>
</video>
{% endraw %}
```
另外我们还要再配置下css，即在website.css中加入
```css
.video-js {
    width:100%;
    height: 100%;
}
```
<br />
{% raw %}
<video id="my-video" class="video-js" controls preload="auto" width="100%" poster="https://zhangjikai.com/resource/poster.jpg" data-setup='{"aspectRatio":"16:9"}'>
  <source src="http://111.com/resource/demo.mp4" type='video/mp4' >
  <p class="vjs-no-js">
    To view this video please enable JavaScript, and consider upgrading to a web browser that
    <a href="https://videojs.com/html5-video-support/" target="_blank">supports HTML5 video</a>
  </p>
</video>
{% endraw %}

## 21. Include-csv
展示 csv 文件。

[插件地址](https://www.npmjs.com/package/gitbook-plugin-include-csv)

```json
{
    "plugins": ["include-csv"]
}
```
example1
{% includeCsv src="./assets/csv/test.csv" %}{% endincludeCsv %}
example2
{% includeCsv %}
hoge,fuga
a,0001
b,002
{% endincludeCsv %}

example3
Arguments
name	description	example
src	The file path for including CSV file.	"./filename.csv"
linkSrc	Link to CSV file above the table.	"true"
encoding	character encoding in CSV file.	"shift_jis"
useHeader	use 1st row for header.	"true"
exHeaders	define column headers.	"col01,col02"
limit	load limit number of rows.	5
usage example
Show the table from csv file, 1st row is header, file's encoding is shift_jis(japanese traditional encoding format).

```html
{% includeCsv src="./sample_records.csv", encoding="shift_jis", useHeader="true" %}{% endincludeCsv %}
```
example4
从标签正文显示表格，行是标题。

{% includeCsv useHeader="true" %}
c1,c2,c3
1,1,1
2,2,2
{% endincludeCsv %}
example5
从 csv 文件显示表格，定义列标题目录，设置行数限制。

```html
{% includeCsv
src="./train.1.csv",
exHeaders="PassengerId,Survived,Pclass,Name,Sex,Age,SibSp,Parch,Ticket,Fare,Cabin,Embarked",
limit=2 %}
{% endincludeCsv %}
```

## 22. Emphasize
为文字加上底色

[插件地址](https://www.npmjs.com/package/gitbook-plugin-emphasize)
```json
{
  "plugins": [
    "emphasize"
  ]
}
```
使用示例:

This text is {% em %}highlighted !{% endem %}

This text is {% em %}highlighted with **markdown**!{% endem %}

This text is {% em type="green" %}highlighted in green!{% endem %}

This text is {% em type="red" %}highlighted in red!{% endem %}

This text is {% em color="#ff0000" %}highlighted with a custom color!{% endem %}

## 23. Graph

使用 function-plot 绘制数学函数图。

[插件地址](https://www.npmjs.com/package/gitbook-plugin-graph)  
[function-plot](https://mauriciopoppe.github.io/function-plot/)

```json
{
    "plugins": [ "graph" ]
}
```

下面是一个示例，需要注意的是 `{% graph %}` 块中的内容必须是合法的 JSON 格式。
```
{% graph %}
{
    "title": "1/x * cos(1/x)",
    "grid": true,
    "xAxis": {
        "domain": [0.01, 1]
    },
    "yAxis": {
        "domain": [-100, 100]
    },
    "data": [{
        "fn": "1/x * cos(1/x)",
        "closed": true
    }]
}
{% endgraph %}
```

效果如下所示：
{% graph %}
{
"title": "1/x * cos(1/x)",
"grid": true,
"xAxis": {
"domain": [0.01, 1]
},
"yAxis": {
"domain": [-100, 100]
},
"data": [{
"fn": "1/x * cos(1/x)",
"closed": true
}]
}
{% endgraph %}

## 24. Chart
使用 C3.js 或者 Highcharts 绘制图形。

[插件地址](https://www.npmjs.com/package/gitbook-plugin-chart)  
[C3.js](https://github.com/c3js/c3)  
[highcharts](https://github.com/highcharts/highcharts)

```json
{
    "plugins": [ "chart" ],
    "pluginsConfig": {
        "chart": {
            "type": "c3"
        }
    }
}
```
type 可以是 `c3` 或者 `highcharts`, 默认是 `c3`.

下面是一个示例：
```html
{% chart %}
{
    "data": {
        "type": "bar",
        "columns": [
            ["data1", 30, 200, 100, 400, 150, 250],
            ["data2", 50, 20, 10, 40, 15, 25]
        ],
        "axes": {
            "data2": "y2"
        }
    },
    "axis": {
        "y2": {
            "show": true
        }
    }
}
{% endchart %}
```
效果如下所示：
{% chart %}
{
"data": {
"type": "bar",
"columns": [
["data1", 30, 200, 100, 400, 150, 250],
["data2", 50, 20, 10, 40, 15, 25]
],
"axes": {
"data2": "y2"
}
},
"axis": {
"y2": {
"show": true
}
}
}
{% endchart %}

## 25. Donate
打赏插件  
[插件地址](https://www.npmjs.com/package/gitbook-plugin-donate)
```json
{
  "plugins": [
    "donate"
  ],
  "pluginsConfig": {
    "donate": {
      "wechat": "https://111.com/resource/weixin.png",
      "alipay": "https://111.com/resource/alipay.png",
      "title": "给爷",
      "button": "赏",
      "alipayText": "支付宝打赏",
      "wechatText": "微信打赏"
    }
  }
}
```

## 26. Musicxml
支持 musicxml 格式的乐谱渲染。

[插件地址](https://www.npmjs.com/package/gitbook-plugin-musicxml)  
[musicXML](http://www.musicxml.com/)

```json
{
    "plugins": ["musicxml"]
}
```

下面是一个示例，需要注意的是 block 中的内容必须是一个合法的 musicxml 文件路径，并且不能有换行和空格。
```
{% musicxml %}assets/musicxml/mandoline - debussy.xml{% endmusicxml %}
```
效果如下所示
{% musicxml %}assets/musicxml/mandoline - debussy.xml{% endmusicxml %}

## 27. auto-scroll-table
表格增加滑动条

[插件地址](https://www.npmjs.com/package/gitbook-plugin-auto-scroll-table)  

```json
{
    "plugins": ["auto-scroll-table"]
}
```

## 28. Github
添加github图标

[插件地址](https://www.npmjs.com/package/gitbook-plugin-github)
```json
{
  "plugins": [
    "github"
  ],
  "pluginsConfig": {
    "github": {
      "url": "https://github.com/Skynetset"
    }
  }
}
```

## 29. page-treeview
一个用于为每个页面生成“树视图”的 gitbook 插件。
![](https://raw.githubusercontent.com/aleen42/gitbook-treeview/master/1.png)
[插件地址](https://www.npmjs.com/package/gitbook-plugin-page-treeview)
```json
{
  "plugins": [
    "page-treeview"
  ],
  "pluginsConfig": {
    "page-treeview": {
      "copyright": "Copyright &#169; Skynetcus",
      "minHeaderCount": "2",
      "minHeaderDeep": "2"
    }
  }
}
```

## 30. lightbox
一个通过灯箱显示图像的 gitbook 插件

[插件地址](https://www.npmjs.com/package/gitbook-plugin-lightbox)
```json
{
  "plugins": [
    "lightbox"
  ],
  "pluginsConfig": {
    "pluginsConfig": {
      "lightbox": {
        "includeJQuery": false,
        "options": {
          "resizeDuration": 200,
          "sameUuid": true,
          "wrapAround": true
        }
      }
    }
  }
}
```

## Github Buttons
添加项目在 github 上的 star，watch，fork情况

[插件地址](https://plugins.gitbook.com/plugin/github-buttons)

```json
{
    "plugins": [
        "github-buttons"
    ],
    "pluginsConfig": {
        "github-buttons": {
            "repo": "Skynetcus/gitbook-use",
            "types": [
                "star",
                "watch",
                "fork"
            ],
            "size": "small"
        }
    }
}
```

## Include Codeblock
使用代码块的格式显示所包含文件的内容. 该文件必须存在。插件提供了一些配置，可以区插件官网查看。如果同时使用 ace 和本插件，本插件要在 ace 插件前面加载。

[插件地址](https://plugins.gitbook.com/plugin/include-codeblock)
```json
{
    "plugins": [
        "include-codeblock"
    ],
    "pluginsConfig": {
        "include-codeblock": {
            "template": "ace",
            "unindent": "true",
            "theme": "monokai"
        }
    }
}
```
使用示例:

[import](styles/website.css)

## Splitter
使侧边栏的宽度可以自由调节

![](https://raw.githubusercontent.com/yoshidax/gitbook-plugin-splitter/master/gitbook-splitter-demo.gif)

[插件地址](https://plugins.gitbook.com/plugin/splitter)
```json
{
  "plugins": [
    "splitter"
  ]
}
```

## Favicon
更改网站的 favicon.ico  
[插件地址](https://plugins.gitbook.com/plugin/favicon)
```json
{
    "plugins": [
        "favicon"
    ],
    "pluginsConfig": {
        "favicon": {
            "shortcut": "assets/images/favicon.ico",
            "bookmark": "assets/images/favicon.ico",
            "appleTouch": "assets/images/apple-touch-icon.png",
            "appleTouchMore": {
                "120x120": "assets/images/apple-touch-icon-120x120.png",
                "180x180": "assets/images/apple-touch-icon-180x180.png"
            }
        }
    }
}
```

## Todo
添加 Todo 功能。默认的 checkbox 会向右偏移 2em，如果不希望偏移，可以在 `website.css` 里加上下面的代码:
```css
input[type=checkbox]{
    margin-left: -2em;
}
```
[插件地址](https://plugins.gitbook.com/plugin/todo)

```json
{
  "plugins": [
    "todo"
  ]
}
```
使用示例：
- [ ] write some articles
- [x] drink a cup of tea

## Terminal
模拟终端显示，主要用于显示命令以及多行输出，不过写起来有些麻烦。

[插件地址](https://plugins.gitbook.com/plugin/terminal)
```json
{
    "plugins": [
        "terminal"
    ],
    "pluginsConfig": {
        "terminal": {
            "copyButtons": true,
            "fade": false,
            "style": "flat"
        }
    }
}
```

现在支持 6 种标签：
* command: Command "executed" in the terminal.
* delimiter: Sequence of characters between the prompt and the command.
* error: Error message.
* path: Directory path shown in the prompt.
* prompt: Prompt of the user.
* warning: Warning message.

标签的使用格式如下所示：
```
**[<tag_name> 内容]
```
为了使标签正常工作，需要在代码块的第一行加入 `**[termial]` 标记，下面是一个完整的示例：

<pre>```
**[terminal]
**[prompt foo@joe]**[path ~]**[delimiter  $ ]**[command ./myscript]
Normal output line. Nothing special here...
But...
You can add some colors. What about a warning message?
**[warning [WARNING] The color depends on the theme. Could look normal too]
What about an error message?
**[error [ERROR] This is not the error you are looking for]
```</pre>

效果如下所示：
```
**[terminal]
**[prompt foo@joe]**[path ~]**[delimiter  $ ]**[command ./myscript]
Normal output line. Nothing special here...
But...
You can add some colors. What about a warning message?
**[warning [WARNING] The color depends on the theme. Could look normal too]
What about an error message?
**[error [ERROR] This is not the error you are looking for]
```

terminal 支持下面 5 种样式，如果需要更换样式，在 pluginsConfig 里配置即可。
* black: Just that good old black terminal everybody loves.
* classic: Looking for green color font over a black background? This is for you.
* flat: Oh, flat colors. I love flat colors. Everything looks modern with them.
* ubuntu: Admit it or not, but Ubuntu have a good looking terminal.
* white: Make your terminal to blend in with your GitBook.

## Copy-code-button
为代码块添加复制的按钮。

[插件地址](https://plugins.gitbook.com/plugin/copy-code-button)

```json
{
    "plugins": ["copy-code-button"]
}
```
效果如下图所示：

![](assets/images/copy-code-button.png)

## Alerts
添加不同 alerts 样式的 blockquotes，目前包含 info, warning, danger 和 success 四种样式。

[插件地址](https://plugins.gitbook.com/plugin/alerts)

```json
{
    "plugins": ["alerts"]
}
```
下面是使用示例：
```
Info styling
> **[info] For info**
>
> Use this for infomation messages.

Warning styling
> **[warning] For warning**
>
> Use this for warning messages.

Danger styling
> **[danger] For danger**
>
> Use this for danger messages.

Success styling
> **[success] For info**
>
> Use this for success messages.
```
效果如下所示：

Info styling
> **[info] For info**
>
> Use this for infomation messages.

Warning styling
> **[warning] For warning**
>
> Use this for warning messages.

Danger styling
> **[danger] For danger**
>
> Use this for danger messages.

Success styling
> **[success] For info**
>
> Use this for success messages.

## Versions-select
添加版本选择的下拉菜单，针对文档有多个版本的情况。

[插件地址](https://plugins.gitbook.com/plugin/versions-select)

```
{
    "plugins": [ "versions-select" ],
    "pluginsConfig": {
        "versions": {
            "options": [
                {
                    "value": "http://gitbook.111.com",
                    "text": "v3.2.2"
                },
                {
                    "value": "http://gitbook.111.com/v2/",
                    "text": "v2.6.4"
                }
            ]
        }
    }
}
```

我们可以自定义 css 来修改 select 的显示样式：
```css
.versions-select select {
    height: 2em;
    line-height: 2em;
    border-radius: 4px;
    background: #efefef;
}
```

效果见左上角。

## RSS
添加 rss 订阅功能。

[插件地址](https://plugins.gitbook.com/plugin/rss)

```json
{
    "plugins": [ "rss" ],
    "pluginsConfig": {
        "rss": {
            "title": "GitBook 使用教程",
            "description": "记录 GitBook 的配置和一些插件的使用",
            "author": "Skynetcus",
            "feed_url": "http://gitbook.111.com/rss",
            "site_url": "http://gitbook.111.com/",
            "managingEditor": "me@111.com",
            "webMaster": "me@111.com",
            "categories": [
                "gitbook"
            ]
        }
    }
}
```
效果见右上角。

## theme-comscore

主题插件, 修改标题和表格颜色。默认标题都是黑色的。

[插件地址](https://plugins.gitbook.com/plugin/theme-comscore)

``` json
{
"plugins": [
        "theme-comscore"
    ]
}
```

## summary

根据文件自动生成目录。

[插件地址](https://plugins.gitbook.com/plugin/summary)

``` json
{
"plugins": [
        "summary"
    ]
}
```
规则：

- 每个新增的目录中加入`README.md`，否则菜单为不可折叠
- 同个目录下的文件采用自然排序来决定菜单生成的前后顺序， 故在文件或目录前加入 "数字-" 如 "0-" 或 "1-" 来排序菜单的前后顺序。
- 菜单由目录自动生成，菜单名称依赖md文件中的标题， 故每个md文件中必须添加标题, 否则无法生成目录。

示例：

我们假设您的源代码树是这样完成的：

``` bash
$ tree .
.
├── 1-Getting Started
│   ├── 0-README.md
│   └── 1-TEST.md
├── 2-Reference
│   └── 0-README.md
├── README.md
└── SUMMARY.md
```

生成的SUMMARY.md文件将如下所示：
``` bash
- [Getting Started](1-Getting Started/0-README.md)
    - [Test](1-Getting Started/1-TEST.md)
- [Reference](2-Reference/0-README.md)
```