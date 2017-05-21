#H5新增元素
#
##构建主体内容

####article元素

article:常用于博客中的 一篇文章，论坛中的 一个帖子，或者浏览者的 一段评论等， 表示独立的内容区块，通常包含头部(header)和底部元素(footer)

####section元素

1.section:需要包含一个标题(hn)元素，一般不用包含头部和底部元素，通常为那些有标题的元素内容进行分段

2.section和article的区别

  * article代表文档，页面或者应用程序中独立完整的可以被外部引用的内容，强调内容独立完整性。
  * section对页面上的内容进行分块处理，如对文章分段等，相邻的section应该是相关的。
```
<article>
    <header>
        <h1>潜行者的个人介绍</h1>
    </header>
    <p>潜行者2是一个中国人，是一个帅哥....dygfrUS日日女热死你葌UR好闺女UR给女方 UR个为还能出租或引入UR股女 </p>
    <section>
        <h2>评论</h2>
        <article>
            <h3>评论者：潜行者3</h3>
            <p>确实真的很帅</p>
        </article>
        <article>
            <h3>评论者：潜行者4</h3>
            <p>今天吃药了吗</p>
        </article>
    </section>
    <footer>江西潜水协会</footer>
</article>
```

####nav元素

是一个可以用于页面导航的链接组，其中导航元素链接到当前页面的其他部分或者其他页面，不是所有的链接都要放到链接组，只需要主要的，基本的链接组放进nav里面即可。 

```
<h1>技术资料</h1>
<!-- 链接到其他页面导航 -->
<nav>
    <ul>
        <li><a href="#">首页</a></li>
        <li><a href="#">博客</a></li>
    </ul>
</nav>
<article>
    <header>h5+css3</header>
    <!-- 文章中的导航 -->
    <nav>
        <ul>
            <li><a href="#h5"></a></li>
            <li><a href="#css3"></a></li>
        </ul>
    </nav>
    <section>
        <h2 id="h5">h5</h2>
        <p>UR如翡翠城图书馆凝聚沪深国际经济哦 人头狗刘素华</p>
    </section>
    <section>
        <h2 id="css3">css3</h2>
        <p>rsiycmkd关于日岁末放大镜看一个人回复奇偶的课程fig</p>
    </section>
</article>
```

####aside元素

用来表示当前页面或者其他页面的附属信息部分。可以包含当前页面或者主要内容相关的引用，侧边栏，广告，导航条以及其他类似的有别于主要内容的部分。

  * 作为主要内容的附属信息部分，包含在article中，其中的内容可以是与当前文章有关的参考资料和名词解释等。

  * 作为页面或者站点全局的附属信息部分，在article之外使用，最典型的是侧边栏，其中可以有友情链接，博客中的其他文章列表，广告单元等。
  
```
<!-- 作为页面或者全局站点的附属信息 -->
<aside>
    <nav>
        <h2>友情链接</h2>
        <ul>
            <li><a href="#">baidu</a></li>
            <li><a href="#">baidu</a></li>
            <li><a href="#">baidu</a></li>
        </ul>

    </nav>
```

####设计微格式

1.H5增加了一种新元素来无歧义的明确的对机器的日期和时间进行编码，这个元素是time元素。

2.time元素代表24小时中某个时刻(年月日时分秒)或者某个日期(年月日)，表示时刻时允许有时差。可以定义很多格式的时间。 

3.datatime属性中日期和时间之间要用T间隔，加字母Z表示UTC时间。

```
<time datetime="2012-11-13">2012年11月13号</time>
<time datetime="2012-11-13">11月13号</time>
<time datetime="2012-11-13">我的生日</time>
<time datetime="2012-11-13T20:00">我的生日是晚上八点</time>
<time datetime="2012-11-13T20:00Z">我的生日是晚上八点</time>
<time datetime="2012-11-13T20:00+9:00">我的生日是晚上八点的美国时间</time>
```

4.添加发布日期(pubdate属性)
  
  * pubdate属性是一个可选的布尔值属性，可用在article元素中time元素中，意思是time元素代表了文章或整个页面的发布日期。
  
  * 由于time元素不仅仅表示发布时间，还可以表示其他用途的时间，如通知约会等，为了避免引擎误解发布日期，使用pubdate还可以显示告诉引擎文章哪个是正确的发布日期。

```
<article>
    <header>
        <h1>谷歌董事长密令:每天关机一小时</h1>
        <p>发布日期<time date="2012-5-20" pubdate>2012年5月20日</time></p>
        <p>关于<time date="2012-5-23" pubdate>2012年5月23日</time>更正通知</p></header>
    <p>㒑rg89ah局融合女热加工费风湿热一个iOS人规划出嗨哟个人狙后入式恢复仍</p>
    <footer>
        <p>http://www.github.com</p>
    </footer>
</article>
```


#
##添加语义模块

####标题块header

具有引导和导航作用的结构元素，通常用来放置整个页面或者页面内的一个内容的区块标题。

####标题分组hgroup
为标题及其子标题进行分组，通常与h1-h6联系

####脚注块footer
内容块的注脚，如父级内容添加注释，或者给网页添加版权信息，脚注信息有多种形式，如作者，相关阅读链接及版权信息。

####联系信息addresss
在文档中定义联系信息包括文档作者，文档编辑者名称，电子邮箱，真实的地址电话号码


#
#
#
#h5表单
#
###新增的input类型

1.原来有的input类型

  * text 单行输入文本域
  * password 密码域
  * radio 单选框
  * checkbox 复选框
  * submit 提交按钮
  * reset 重置按钮
  * image 图片提交按钮
  * button 普通按钮
  * hidden 定义隐藏的字段
  * file 上传文件
  * select-option

2.新增的input类型

  * email类型 专门用于输入email的文本输入域，在提交表单时，会自动验证email的值，如果不是有效的值，则不会提交该表单
  * url类型 提供用于输入url地址的这类特殊文本的文本框，
  * number类型 提供用于输入数值的文本框，有min,max,step,value属性
  * range类型 

     * 提供用于输入包含一定范围内数字值的文本框，有min,max,step,value属性
     * number和range都是数值的文本框，他们区别主要是在浏览器中的显示形式不一样，range显示为滑动条。
  
  * search类型 用于输入搜索关键字的文本框
  * tel类型 用于专门用于输入电话号码的文本框，不限定于数字
  * color类型 专门用于用于设置颜色的文本框，可以快速打开拾色面板
  * datepickers日期检出器类型(包含属性max,min,step,value)
    
    * date类型 用于选取年月日的，选择一个具体日期
    * time类型 用于选取时间的，具体到小时和分钟
    * week类型 选取周年
    * month 选取年月，选择具体月份
    * datetime类型 选取时间，年月日，其中时间指UTC时间（Z）
    * datetime-local类型：选取时间，年月日，其中时间指本地时间

#
###新增input属性

1.autocomplete属性 自动完成功能，属性值有on,off,空值三种

2.autofocus属性 自动获得焦点，以方便输入搜索关键词，

3.form属性 表示所属的表单，属性值为所属表单的id

4.表单重写属性
   
   * formaction
   * formenctype
   * formmethod
   * formnovalidate
   * formtarget

5.height和width属性 只能用于image类型的提交按钮

6.min,max和step属性 适用于datepickes,number,range

7.multiple属性 复选属性，file,select

8.pattern属性 用于验证input类型输入框用户输入的内容是否与自定义的正则表达式相匹配

9.placeholder属性 占位符，在输入框为空时显式出现，当获得焦点时会消失

10.required属性 规定用户输入的内容不能为空

11.list属性 表示输入框所属的datalist,属性值为datalist的id

#
###新增的表单元素

1.datalist元素
   
   * datalist，option与list相匹配使用
   * 每一个option元素必须先设置value值

2.keygen元素

  * 密匙对生成器，能够使用户验证更为可靠

3.output元素

  * 用于在浏览器中显示计算结果或脚本输出

#
###新增的表单(form)属性

1.autocomplete属性(on/off)
   
   * 用于规定form中所有元素都拥有自动完成功能
   * 如果要使某个别元素关闭自动完成功能，则单独为该元素设置autocomplete为off即可

2.novalidate属性 (true/false) 用于在提交表单时取消对整个表单的验证

#
#
#canvas元素
