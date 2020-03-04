>微信公众号：**[justpic]**
关注python、关注`justpic`。问题或建议，请公众号留言。
Markdown是一种轻量级标记语言。你不需要关心标题多大字号，段前距多少，列表缩进几格，只要在纯文本前后增加一些标记符号（例如 # - * >)，就能轻松写出工整精美的文章。与富文本编辑器（例如Word）是通过点击图形化的功能按钮来实现排版，而Markdown则是通过标记字符去赋予文字不同格式。易读易写（easy-to-read and easy-to-write),让任何与文字打交道的人专注于写作，不用操心排版，这一点类似vi编辑器功能。

<!--more-->
本文主要从Markdown主要特点、入门语法、写作结构大纲、应用场景四个方面对Markdown写作指南进行详细介绍。
### Markdown 主要特点
Markdown主要有以下三大特点：  
**特点1. 格式统一**  
同一份Word文档，在
+ 不同的设备：Windows、macOS、Android、iOS
+ 不同的版本：旧版Word、新版Word
+ 不同的软件：Microsoft Office、WPS
可能显示不一样的效果。而Markdown可以Write once,export everywhere。不管在电脑上，还是手机上，用Markdwon写出来的文章都能带来舒适、统一、美好的阅读体验。

**特点2. 向外兼容**  
可以导出PDF、Word、HTML、图片等格式分享给没有安装Markdown编辑器的人，强烈推荐使用pandoc工具进行markdown文档的转换。

**特点3. 直接支持html,css**  
Markdown是直接支持在markdown文档中使用html和css语言的：
- 语法：
```
<a href="#jump_1">来个页内跳转</a>，跳转到文未的：`<a id="jump_1">我是页内跳转到的位置</a>` ,对应：`id="jump_1"`
<span  style="color: #5bdaed; ">先给点颜色你看看</span>
<span  style="color: #AE87FA; ">再给点颜色你看看</span>
<span  style="font-size:1.3em;">试试改变字体大小</span>
<span  style="font-size:1.3em;font-weight: bold;">改变字体大小，再来个粗体又如何？</span>

<p style="text-align:center">
试试内容居中

</p>

<p style="text-align:right">
那内容居右呢？
</p>

<p style="text-align:center;color:#1e819e;font-size:1.3em;font-weight: bold;">
来个综合的试试
<br/>
第二行
</p>
***
<a id="jump_1">我是页内跳转到的位置</a>
```
- 预览效果：   
    <a href="#jump_1">来个页内跳转</a>，跳转到文未的：`<a id="jump_1">我是页内跳转到的位置</a>` ,对应：`id="jump_1"`
    <span  style="color: #5bdaed; ">先给点颜色你看看</span>
    <span  style="color: #AE87FA; ">再给点颜色你看看</span>
    <span  style="font-size:1.3em;">试试改变字体大小</span>
    <span  style="font-size:1.3em;font-weight: bold;">改变字体大小，再来个粗体又如何？</span>
    
    <p style="text-align:center">
    试试内容居中
    
    </p>
    
    <p style="text-align:right">
    那内容居右呢？
    </p>
    
    <p style="text-align:center;color:#1e819e;font-size:1.3em;font-weight: bold;">
    来个综合的试试
    <br/>
    第二行
    </p>
    
    ***
    <a id="jump_1">我是页内跳转到的位置</a>

### Markdown入门语法
**1.标题、列表、引用**    

标记符号|标记结果
---|----
`# + 空格 + 文本`|一级标题
`##+空格+文本`|二级标题
`###+空格+文本`|三级标题
`-+空格+文本`|无序列表
`1+.+空格+文本`|有序列表
`>+空格+文本`|引用
- 标题   
支持6种大小的标题，分别对应`#`,`##`,`###`,`####`,`#####`,`######`，和样式文件中的`h1,...,h6`如：
    ```javascript
    ##### H5
    ###### H6
    #### 行内代码
    ```

- 列表
    - 无序列表  
    建议使用-作为无须列表，型号*可能和加粗和斜体符号产生混淆，加号+不流行。
    - 有序列表  
        语法一（手动排序）：`1+.+空格+文本`       
            1. 斜月沉沉藏海雾，碣石潇湘无限路。
            2. 不知乘月几人归，落月摇情满江树。
            3. 春江潮水连海平，海上明月共潮生。           
        语法二（自动排序）  
        对于比较长的、可能会修改的列表（尤其是很长的嵌套列表），请使用`懒人编号法`。纵使有新的列表项`插队`,把序号弄乱了也没关系，Markdown编辑器自动会对序号进行纠错。   
        语法说明：  
        ```
        1. Foo.
        1. Bar.
            1. Foofoo.
            1. Barbar. 
            1. Gargar
        1. Baz. 
        ```
        预览效果：  
        1. Foo.
        1. Bar.
            1. Foofoo.
            1. Barbar. 
            1. Gargar
        1. Baz. 
    - 嵌套列表  
        缩进2~4个空格或一个Tab（推荐），可以嵌套列表   
        示例一 
        ```
        1. 不知乘月几人归，落月摇情满江树。
            - 与君吟弄风月，端不负平生。
            - 对秋深，离恨苦，数夜满庭风雨。
            - 五月畬田收火米，三更津吏报潮鸡。
        2. 人姝丽，粉香吹下，夜寒风细。
            - 弓弦抱汉月，马足践胡尘。
            - 寒月悲笳，万里西风瀚海沙。
            - 东堂坐见山，云风相吹嘘。
        ```
        预览效果：  
        1. 不知乘月几人归，落月摇情满江树。  
            - 与君吟弄风月，端不负平生。  
            - 对秋深，离恨苦，数夜满庭风雨。    
            - 五月畬田收火米，三更津吏报潮鸡。
        2. 人姝丽，粉香吹下，夜寒风细。
            - 弓弦抱汉月，马足践胡尘。
            - 寒月悲笳，万里西风瀚海沙。
            - 东堂坐见山，云风相吹嘘。
- 引用
在每一行使用`>`符号，包括换行的句子
        
**2.特殊说明的文字**

标记符号|标记结果   
---|---
`**+加粗+**`|**加粗**
`*+斜体+*`|*斜体*
`~~+删除线+~~`| ~~删除线~~

**3.任务列表**  
Markdown支持任务列表  
语法：
```
- [ ] 纯牛奶
- [x] 西瓜
- [ ] 鸡蛋
- [ ] 保鲜膜
- [ ] 猪肉
```
预览效果：    
- [ ] 纯牛奶
- [x] 西瓜
- [ ] 鸡蛋
- [ ] 保鲜膜
- [ ] 猪肉

**4.表格**  
<!--adsense-->
语法：  
```
|左对齐|居中对齐|右对齐|
|:---|:---:|----:|
|**加粗**|[插入连接]（https://)|5.7|
|`换行`<br/>下一行|![插入图片](ht图片上：//）|10.4|

```
预览效果：  

|左对齐|居中对齐|右对齐|
|:-----|:-----:|----:|
|**加粗**|[插入连接]（https://)|5.7|
|`换行`<br/>下一行|![插入图片](ht图片上：//）|10.4|  

**5.代码**
- 行内代码
    - 用两个重音符`（backtick，在Tab键上方)包裹
    ```javascript
        `Markdown`是一种轻量级标记语言
    ```
    - 预览  
     `Markdown`是一种轻量级标记语言
    - 重音符前后空一格  
    ```javascript
    - 推荐：使用键盘快捷键 `Ctrl+D` 可以将当前网页保存为书签。
    - 反对：使用键盘快捷键`Ctrl+D`可以将当前网页保存为书签。
    ```
      - 推荐：使用键盘快捷键 `Ctrl+D` 可以将当前网页保存为书签。
      - 反对：使用键盘快捷键`Ctrl+D`可以将当前网页保存为书签。
- 代码块  
    将三个重音符`置于代码块的首行和末行  
    ```javascript
      print "Hello,python!"
    ```

**6.强制换行**    
在行末使用空格（两个以上）+换行(Enter)    
预览效果：  

```javascript
   `enticing` 
   - Her neck was short but rounded and her arms plump and enticin
     他的脖子短，但浑圆可爱；两臂丰腴，也很动人。by《飘》
   - This was enticing to Wozniak,even more than any prospect of getting rich.  
     这句话对沃兹尼亚克的诱惑太大了，比变成富人的诱惑还要大。by《乔布斯传》
```

注：markdown对代码块的语法是开始和结束行都要添加：\`\`\`,其中 \` 为windows键盘左上角那个，如下：


如果要精确指定语言（如：`java,cpp,css,xml,javascript,python,php,go,kotlin,lua,objectivec`等等）时，在头部直接指定，如：\`\`\`javascript，如下：

    ```javascript
    function showSnackbar() {
      var $snackbar = $('#snackbar');
      $snackbar.addClass('show');
      setTimeout(() => {
        $snackbar.removeClass('show');
      }, 3000);
    }
    ```

**7.外链的超链接**
试试外链的超链接：[我是外链的超链接](http://blog.qikqiak.com),markdown对链接的语法为：`\[\]()`,如：`\[我是外链的超链接\](http://blog.qikqiak.com)`

**8.页内的超链接**
试试页内的超链接：[我是页内的超链接](#jump_1)，注：你先要在要跳转的到地方放置一个类似：`<a id="jump_1">任意内容</a>`的锚点。由`id="jump_1" `来匹配。

**9.分隔线**  
语法：
```javascript
***
```
预览效果：  
***
**10.符号说明**  
<!--adsense-->
Markdown针对特殊符号具有转义定义，具体解释如下表：

符号|说明|对应编码
---:|---:|---
&|AND 符号|& amp;	
<|小于	  |& lt;
&nbsp;|空格|& nbsp;
¿|倒问号	|& iquest;
?|问号	|& quest;
«|左书名号|& laquo;
»|右书名号|& raquo;
“|引号	|& quot;
‘|左单引号|& lsquo;
’|右单引号|& rsquo;
“|左双引号|& ldquo;
”|右双引号|& rdquo
¶|段落符号|& para;
§|章节符	|& sect;
×|乘号	|& times;
÷|除号	|& divide;
±|加减号	|& plusmn;
ƒ|function|& fnof;	
√|根号	|& radic;
∞|无穷大	|& infin;
°|度	|& deg;	
≠|不等号	|& ne;	
≡|恒等于	|& equiv;
≤|小于等于|& le;	
≥|大于等于|& ge;
⊥|垂直符号|& perp;	
←|左箭头	|& larr;	
→|右箭头	|& rarr;	
↑|上箭头	|& uarr;	
↓|下箭头	|& darr;	
↔|水平箭头|& harr;	
↕|竖直箭头|& varr;
⇐|双线左箭头|& lArr;	
⇒|双线右箭头|& rArr;
⇑|双线上箭头|& uArr;
⇓|双线上箭头|& dArr;
⇔|双线水平双箭头	|& hArr;
⇕|双线竖直箭头|& vArr;
♠|黑桃	|& spades;
♥|红桃	|& hearts;
♣|梅花	|& clubs;
♦|方块	|& diams;
©|版权	|& copy;
®|注册商标|& reg;
™|商标	|& trade;
¥|人民币	|& yen;	
€|欧元	|& euro;
¢|美分	|& cent;
£|英磅	|& pound;
⊕||& oplus;|	
½|	二分之一	|& frac12;
¼|	四分之一	|& frac14;	
‰|	千分符号	|& permil;	
∴|	所以	|& there4;
π|	圆周率	|& pi;	
¹|	上标1	|& sup1;	
α|	alpha	|& alpha;	
β|	beta	|& beta;	
γ|	gamma	|& gamma;	
δ|	delta	|& delta;	
θ|	theta	|& theta;	
λ|	lambda	|& lambda;	
σ|	sigma	|& sigma;	
τ|	tau	    |& tau;	

### 写作结构大纲  
一般按照如下结构参照Word文档结构进行markdown文档的大纲编写。  
```
### 标题
#### 层级
# 一级标题：文章的标题  
## 二级标题：文章主要部分的大标题  
### 三级标题：二级标题下面一级的小标题  
```  
-  虽然Markdown最大支持######六级标题，为了保持层级的简单，防止出现过于复杂的章节，请谨慎使用四级标题（除非是长文章）。如果三级标题下有并列性的内容，可以使用加粗、有序列表或无序列表代表末级标题。
```
### 三级标题
**四级标题A**
- 论据1（五级标题）
    - 细分论据 1(六级标题)
    - 细分论据 2（六级标题)
    - 细分论据 3(六级标题)
- 论据2
- 论据3

**四级标题B** 
1. 论据
2. 论据
3. 论据

**四级标题C**
- 论据1
- 论据2 
- 论据3

----
### 三级标题（适用于长文章）
#### 四级标题A
#### 四级标题B
#### 四级标题C
```
**文档标题拟定要点**
- 标题要简短，结尾不带标点符号。
- （源码上）标题前后空一行（段前距和段后距）。
- 大标题和小标题之间要有内容过度（引出或概括下文）。  
示例：
```
# Title
开门见山地告诉读者这篇文章讲什么？
一级标题作为文章的（页面）标题（H），并且尽可能和文件名称保持一致。如果文章很长，使用[TOC]生成目录。
## what
先定义问题是什么?...
正文从二级标题开始
## Why
为什么会出现这样的问题?...
## How
下一步该怎么办?...
## See also
文末别忘了贴上参考连接。
* https://link-to-more-info
```  
<!--adsense-text-->
### Markdown应用场景
>6大应用场景

**1.公众号排版**  
- [Markdown Nice](https://mdnice.com/)：让微信排版变 Nice，支持自定义主题 CSS。
- [可能吧公众号 Style 一键转换器](https://knb.im/mp/)：老司机禅叔出品。 
- [md](https://justpic.org/md):自用微信公众号排版  

**2.博客**  

**3.知乎专栏** 

**4.幻灯片**

**5.专业报告**

**6.笔记**

### Markdown推荐编辑器

操作系统|Markdown编辑器
---|---
windows|typora    
android|纯纯写作    
macos/ios|Ulysses  

----
**参考**
- [Markdown 完全入门（上）](https://sspai.com/post/36610)
- [Markdown 完全入门（下）](https://sspai.com/post/36682)
- [为知笔记 Markdown 新手指南](https://www.wiz.cn/feature-markdown.html)
- [Markdown 合集 - 少数派](https://sspai.com/tag/Markdown)
- [Google Markdown 书写风格指南](https://www.jianshu.com/p/3beac9fd6496)
- [Markdown Style Guide by Google](https://github.com/google/styleguide/blob/gh-pages/docguide/style.md)
- [Typora 完全使用详解 - liquid617](https://sspai.com/post/54912) 
- [用markdown可以做什么](https://www.bmpi.dev/dev/what-markdown-can-do/)  

**关联阅读**

- [中文排版指南 - 庭说](https://tingtalk.me/typography/) 
