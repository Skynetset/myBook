# <center>Markdown</center> 
##标题
Markdown 标题有两种格式。

###1、使用 = 和 - 标记一级和二级标题
= 和 - 标记语法格式如下：
```markdown
    我展示的是一级标题
    =================
    我展示的是二级标题
    -----------------
```

<!--sec data-title="标题 1 显示效果" data-id="section0" data-show=true ces-->

我展示的是一级标题
=================
我展示的是二级标题
-----------------

<!--endsec-->

###2、使用 # 号标记
使用 # 号可表示 1-6 级标题，一级标题对应一个 # 号，二级标题对应两个 # 号，以此类推。
```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```
<!--sec data-title="标题 2 显示效果" data-id="section1" data-show=true ces-->

# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题

<!--endsec-->

## 段落
### 两个以上空格加上回车。
```markdown
aaa  
bbb
```

<!--sec data-title="段落 1 显示效果" data-id="section2" data-show=true ces-->
aaa  
bbb
<!--endsec-->

### 空行。
```markdown
aaa

bbb
```

<!--sec data-title="段落 2 显示效果" data-id="section3" data-show=true ces-->
aaa

bbb
<!--endsec-->



## 字体
### Markdown 可以使用以下几种字体：

```markdown
*斜体文本*
_斜体文本_
**粗体文本**
__粗体文本__
***粗斜体文本***
___粗斜体文本___  
~~BAIDU.COM~~
<u>带下划线文本</u>  
```

<!--sec data-title="字体 显示效果" data-id="section4" data-show=true ces-->
*斜体文本*  
_斜体文本_  
**粗体文本**  
__粗体文本__  
***粗斜体文本***  
___粗斜体文本___  
~~BAIDU.COM~~  
<u>带下划线文本</u>  
<!--endsec-->

## 分隔线
### 三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。
可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：  
```markdown
***

* * *

*****

- - -

----------  
```

<!--sec data-title="分隔线 显示效果" data-id="section5" data-show=true ces-->

***

* * *

*****

- - -

----------

<!--endsec-->

## 脚注
脚注是对文本的补充说明。

```markdown
[^要注明的文本]  
以下实例演示了脚注的用法：  
创建脚注格式类似这样 [^脚注]。  
[^脚注]: 人生若只如初现！！！  
```

<!--sec data-title="脚注 显示效果" data-id="section6" data-show=true ces-->  
[^要注明的文本]  
以下实例演示了脚注的用法：  
创建脚注格式类似这样 [^脚注]。  
[^脚注]: 人生若只如初现！！！  
<!--endsec-->

## 列表
Markdown 支持有序列表和无序列表。

### 无序列表
> 使用星号(*)、加号(+)或是减号(-)作为列表标记，这些标记后面要添加一个空格，然后再填写内容：

```markdown
* 第一项
* 第二项
* 第三项

+ 第一项
+ 第二项
+ 第三项

- 第一项
- 第二项
- 第三项  
```  

<!--sec data-title="无序列表 显示效果" data-id="section7" data-show=true ces-->  
* 第一项
* 第二项
* 第三项

+ 第一项
+ 第二项
+ 第三项

- 第一项
- 第二项
- 第三项  
<!--endsec-->

### 有序列表
> 使用数字并加上 . 号来表示，如：  
```markdown
1. 第一项
2. 第二项
3. 第三项
```  
<!--sec data-title="有序列表 显示效果" data-id="section8" data-show=true ces-->  
1. 第一项
2. 第二项
3. 第三项
<!--endsec-->  

###列表嵌套
> 在子列表中的选项前面添加四个空格即可：  
```markdown
1. 第一项：
    - 第一项嵌套的第一个元素
    - 第一项嵌套的第二个元素
2. 第二项：
    - 第二项嵌套的第一个元素
    - 第二项嵌套的第二个元素
```

<!--sec data-title="列表嵌套 显示效果" data-id="section9" data-show=true ces-->
1. 第一项：
    - 第一项嵌套的第一个元素
    - 第一项嵌套的第二个元素
2. 第二项：
    - 第二项嵌套的第一个元素
    - 第二项嵌套的第二个元素
<!--endsec-->  

## 区块引用
### 格式 
段落开头使用 `>` 符号 ，然后后面紧跟一个空格符号：  
```markdown
> 区块引用
> 人生若只如初见  
> 何事悲风秋画扇
```

<!--sec data-title="区块引用 显示效果" data-id="section10" data-show=true ces-->
> 区块引用  
> 人生若只如初见  
> 何事悲风秋画扇
<!--endsec-->  

### 区块嵌套
区块是可以嵌套的，一个 `>` 符号是最外层，两个 `>` 符号是第一层嵌套，以此类推：  
```markdown
> 最外层
> > 第一层嵌套
> > > 第二层嵌套
```

<!--sec data-title="区块嵌套 显示效果" data-id="section11" data-show=true ces-->
> 最外层
> > 第一层嵌套
> > > 第二层嵌套
<!--endsec-->  

### 区块中使用列表  
```markdown
> 区块中使用列表
> 1. 第一项
> 2. 第二项
> + 第一项
> + 第二项
> + 第三项
```

<!--sec data-title="区块列表 显示效果" data-id="section12" data-show=true ces-->
> 区块中使用列表
> 1. 第一项
> 2. 第二项
> + 第一项
> + 第二项
> + 第三项
<!--endsec-->  



###列表中使用区块
如果要在列表项目内放进区块，那么就需要在 `>` 前添加四个空格的缩进。

```markdown
* 第一项
  > 人生若只如初见
  > 何事悲风秋画扇
* 第二项
```
<!--sec data-title="列表区块 显示效果" data-id="section13" data-show=true ces-->
* 第一项
  > 人生若只如初见  
  > 何事悲风秋画扇
* 第二项
<!--endsec-->  

## 代码
### 反引号包起来（`），例如：  
```markdown
`printf()` 函数
```

<!--sec data-title="反引号单行代码 显示效果" data-id="section14" data-show=true ces-->
`printf()` 函数
<!--endsec-->  

### 代码区块
使用 4 个空格或者一个制表符（Tab 键）。  
aaa  
bbb  
ccc  
ddd  
<!--sec data-title="代码区块 显示效果" data-id="section15" data-show=true ces-->
    aaa  
    bbb  
    ccc  
    ddd
<!--endsec-->  

你也可以用 ``` 包裹一段代码，并指定一种语言（也可以不指定）：

    ```javascript
    $(document).ready(function () {
        alert('RUNOOB');
    });
    ```
<!--sec data-title="``` 显示效果" data-id="section16" data-show=true ces-->
```javascript
$(document).ready(function () {
    alert('RUNOOB');
});
```
<!--endsec--> 

## 链接
### 普通链接使用方法如下：  
```markdown
[链接名称](链接地址)

或者

<链接地址>
```

<!--sec data-title="链接 显示效果" data-id="section17" data-show=true ces-->
这是一个链接 [菜鸟教程](https://www.runoob.com)

<https://www.runoob.com>  
<!--endsec--> 


### 高级链接
我们可以通过变量来设置一个链接，变量赋值在文档末尾进行：  

```markdown
这个链接用 1 作为网址变量 [Google][1]
这个链接用 runoob 作为网址变量 [Runoob][runoob]
然后在文档的结尾为变量赋值（网址）

[1]: http://www.google.com/
[runoob]: http://www.runoob.com/
```

<!--sec data-title="高级链接 显示效果" data-id="section18" data-show=true ces-->
这个链接用 1 作为网址变量 [Google][1]  
这个链接用 runoob 作为网址变量 [Runoob][runoob]  
然后在文档的结尾为变量赋值（网址）  

[1]: http://www.google.com/  
[runoob]: http://www.runoob.com/  
<!--endsec-->  

## 图片
### 基础语法格式如下：

```markdown
![alt 属性文本](图片地址)   
![alt 属性文本](图片地址 "可选标题")    
```
开头一个感叹号 !   
接着一个方括号，里面放上图片的替代文字 
接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上选择性的 'title' 属性的文字。 

<!--sec data-title="图片 显示效果" data-id="section19" data-show=true ces-->
![RUNOOB 图标](http://static.runoob.com/images/runoob-logo.png)   
![RUNOOB 图标](http://static.runoob.com/images/runoob-logo.png "RUNOOB")  
<!--endsec-->  


### 图片网址使用变量:

```markdown
这个链接用 1 作为网址变量 [RUNOOB][1].
然后在文档的结尾为变量赋值（网址）
[1]: http://static.runoob.com/images/runoob-logo.png
```

<!--sec data-title="图片变量 显示效果" data-id="section20" data-show=true ces-->
这个链接用 1 作为网址变量 [RUNOOB][1].
然后在文档的结尾为变量赋值（网址）

[1]: http://static.runoob.com/images/runoob-logo.png
<!--endsec-->  


### 使用普通的 img 标签。

```markdown
<img src="http://static.runoob.com/images/runoob-logo.png" width="50%">
```

<!--sec data-title="img标签 显示效果" data-id="section21" data-show=true ces-->
<img src="http://static.runoob.com/images/runoob-logo.png" width="50%">
<!--endsec-->  

## 表格
使用 | 来分隔不同的单元格，使用 - 来分隔表头和其他行。

### 语法格式如下：

```markdown
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |
```
<!--sec data-title="表格 显示效果" data-id="section22" data-show=true ces-->
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |
<!--endsec-->  

### 对齐方式

* -: 设置内容和标题栏居右对齐。    
* :- 设置内容和标题栏居左对齐。    
* :-: 设置内容和标题栏居中对齐。

```markdown
| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 |
```
<!--sec data-title="表格对齐 显示效果" data-id="section23" data-show=true ces-->
| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 单 | 元 | 格 |
| 单 | 元 | 格 |
<!--endsec-->  

## 高级技巧
### 支持的 HTML 元素
不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。

目前支持的 HTML 元素有：`<kbd>` `<b>` `<i>` `<em>` `<sup>` `<sub>` `<br>`等 ，如：

```markdown
使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑
```

<!--sec data-title="kbd 显示效果" data-id="section24" data-show=true ces-->
使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑
<!--endsec-->  

### 转义
Markdown 使用了很多特殊符号来表示特定的意义，如果需要显示特定的符号则需要使用转义字符，Markdown 使用反斜杠转义特殊字符：

```markdown
**文本加粗**
\*\* 正常显示星号 \*\*
```
<!--sec data-title="转义字符 显示效果" data-id="section25" data-show=true ces-->
**文本加粗**    
\*\* 正常显示星号 \*\*    
<!--endsec-->  

Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：

* \   反斜线
* `   反引号
* \*   星号
* _   下划线
* {}  花括号
* []  方括号
* ()  小括号
* \#   井字号
* \+   加号
* \-   减号
* .   英文句点
* !   感叹号


