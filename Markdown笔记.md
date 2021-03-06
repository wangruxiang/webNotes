Markdown-记录一些常用的语法规则
================================== 
*** 
1. 标题
    + # 一级标题
    + ## 二级标题
    + ### 三级标题
    + #### 四级标题
    + ##### 五级标题
    + ###### 六级标题
    + ####### 七级标题  
    <u>你以为有七级标题吗？哈哈哈，你想太多了呢，只有一级标题到六级标题呢！</u>
***
2. 段落：
    - **段落的换行是使用两个以上空格加上回车** 
    - **字体**  
        - *斜体文本*
        _斜体文本_
        - **粗体文本**
        __粗体文本__
        - ***粗斜体文本***
        ___粗斜体文本___
    - **分隔线**  
        - 分隔线可用***  * * *  *****等等；
        ***

        * * *

        *****

        - - -

        ----------
    - **删除线**
        - RUNOOB.COM
        - GOOGLE.COM
        - ~~BAIDU.COM~~
    - **下划线**
        - <u>带下划线文本</u>
    - **脚注**
        - [^要注明的文本]
        - 创建脚注格式类似这样 [^RUNOOB]  

        [^RUNOOB]: 啦啦啦啦，我是卖报的汪如祥，差三分先生!（我是脚注文本）
***
3. 列表：
    - 无序列表使用星号(*)、加号(+)或是减号(-)作为列表标记，如下：
    * 第一项
    * 第二项
    * 第三项
        + 第一项
        + 第二项
        + 第三项
            - 第一项
            - 第二项
            - 第三项
    - 有序列表使用数字并加上 . 号来表示，如下：
    1. 第一项
    2. 第二项
    3. 第三项
***
4. 区块
    - 区块引用是在段落开头使用 > 符号 ，然后后面紧跟一个空格符号，如下：
    > 区块引用  
    > 菜鸟教程  
    > 学的不仅是技术更是梦想  
    - 区块是可以嵌套的，一个 > 符号是最外层，两个 > 符号是第一层嵌套，以此类推，如下：
    > 最外层  
    > > 第一层嵌套  
    > > > 第二层嵌套  
    - 区块中使用列表，如下  
    > 区块中使用列表  
    > 1. 第一项  
    > 2. 第二项  
        - 机智的差三分先生  
        - 帅气的差三分先生  
        - 善良的差三分先生
        - 这里不能再嵌套列表了哦
    > + 第一项  
    > + 第二项  
    > + 第三项  
    - 列表中使用区块，如下：  
        * 第一项  
        > 差三分先生的幸福生活  
        > 你和我就差那三分  
        * 第二项
***
5. 代码  
    - 如果是段落上的一个函数或片段的代码可以用反引号把它包起来（`），例如：  

        `printf()` 函数  
    - 代码区块使用 4 个空格或者一个制表符（Tab 键），
    - 可以用 ``` 包裹一段代码，并指定一种语言（也可以不指定），如下：  
        ```javascript
        $(document).ready(function () {
            alert('差三分先生');
        });
        ```
        ```div
        <div>我就是那个机智帅气的差三分先生。</div>
        ```
***
6. 链接
    - 链接使用方法如下：[链接名称](链接地址)
    或者<链接地址>
    - 这是一个链接： [差三分先生](https://www.cnblogs.com/wangruxiang/)
    - 直接使用链接地址：<https://www.cnblogs.com/wangruxiang/>
    - 高级链接，如下：  
    这个链接用 1 作为网址变量 [Google][1]
    这个链接用 wangrx 作为网址变量 [差三分先生][wangrx]
    然后在文档的结尾为变量赋值（网址）  

    [1]: http://www.google.com/
    [wangrx]: https://www.cnblogs.com/wangruxiang/
***
7. 图片
    - 图片语法格式：
        - 开头一个感叹号 !
        接着一个方括号，里面放上图片的替代文字
        接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上选择性的 'title' 属性的文字。如下：  
        ![图标1](https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=816307122,2233018573&fm=11&gp=0.jpg)  
        ![图标2](https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=59080103,899554825&fm=11&gp=0.jpg "《我是余欢水》")  
        ![alt 差三分先生](http://pic1.win4000.com/pic/b/e0/78a16e5869.jpg)  
        ![alt 差三分先生](http://pic1.win4000.com/pic/b/e0/ef7b87462c.jpg "我是余欢水剧照")
        - 可以像网址那样对图片网址使用变量，如下:  
        这个链接用 wangrx1 作为网址变量 [差三分先生][wangrx1].
        然后在文档的结尾为变量赋值（网址）  

        [wangrx1]: http://pic1.win4000.com/pic/b/e0/78a16e5869.jpg
        - Markdown 还没有办法指定图片的高度与宽度，如果你需要的话，你可以使用普通的 <img> 标签。  
        <img alt="差三分先生图片" src="http://pic1.win4000.com/pic/b/e0/78a16e5869.jpg" width="50%">
***
8. 表格
    - 制作表格使用 | 来分隔不同的单元格，使用 - 来分隔表头和其他行，如下：  

        - |  表头   | 表头  |
          |  ----  | ----  |
          | 单元格  | 单元格 |
          | 单元格  | 单元格 |
    - 设置表格的对齐方式，如下：  
        -: 设置内容和标题栏居右对齐。  
        :- 设置内容和标题栏居左对齐。  
        :-: 设置内容和标题栏居中对齐。  
        | 左对齐 | 右对齐 | 居中对齐 |
        | :-----| ----: | :----: |
        | 单元格 | 单元格 | 单元格 |
        | 单元格 | 单元格 | 单元格 |
***
9. markdown 其他技巧
    - 支持的 HTML 元素：  
    不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。目前支持的 HTML 元素有：`<kbd> <b> <i> <em> <sup> <sub> <br>`等 ，如下：  
        - 使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑
        - 使用 <b>Ctrl</b>+<b>Alt</b>+<b>Del</b> 重启电脑
        - 使用 <i>Ctrl</i>+<i>Alt</i>+<i>Del</i> 重启电脑
        - 使用 <em>Ctrl</em>+<em>Alt</em>+<em>Del</em> 重启电脑
        - 使用 <sup>Ctrl</sup>+<sup>Alt</sup>+<sup>Del</sup> 重启电脑
        - 使用 <sub>Ctrl</sub>+<sub>Alt</sub>+<sub>Del</sub> 重启电脑
        - 使用 <br>Ctrl<br>+<br>Alt<br>+<br>Del<br> 重启电脑
    - 转义
        - Markdown 使用了很多特殊符号来表示特定的意义，如果需要显示特定的符号则需要使用转义字符，Markdown 使用反斜杠转义特殊字符，如下：  
            - **文本加粗**   
            - \*\* 正常显示星号 \*\*
        - Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号，如下：
            - ```\   反斜线```
            - ``` `  反引号```
            - ``` *  星号```
            - ```_   下划线```
            - ```{}  花括号```
            - ```[]  方括号```
            - ```()  小括号```
            - ```#   井字号```
            - ```+   加号```
            - ```-   减号```
            - ```.   英文句点```
            - ```!   感叹号```
    - 公式
        - 当你需要在编辑器中插入数学公式时，可以使用两个美元符 $$ 包裹 TeX 或 LaTeX 格式的数学公式来实现。提交后，问答和文章页会根据需要加载 Mathjax 对数学公式进行渲染。如下：  
        $$
        \mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
        \mathbf{i} & \mathbf{j} & \mathbf{k} \\
        \frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
        \frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
        \end{vmatrix}
        ${$tep1}{\style{visibility:hidden}{(x+1)(x+1)}}
        $$
***
10. 流程图、时序图(顺序图)、甘特图
    - ```mermaid
graph LR
A[方形] -->B(圆角)
    B --> C{条件a}
    C -->|a=1| D[结果1]
    C -->|a=2| E[结果2]
    F[横向流程图]
```

 
