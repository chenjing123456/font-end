#CSS

1.文字属性：font:style weight size family
    
  * 文字字体如果需要给中文和英文分别设置字体，则font-family:英文字体 中文字体（备选方案）;
  
  * 文本属性：text-decoration/align/indent.
  
2.选择器

  * 后代选择器：（选择器1 选择器2）先找到所有的1，再从1中找到所有的后代2
  * 子元素选择器：（选择器1>选择器2）先找到所有的1，再从1中找到所有的选择器为2的子元素
  * 序选择器   
    
    * 同级别的第几个： ( :first-child;:last-child;:nth-child(n);:nth-last-child(n);:only-child;)  
    * 同级别同类型的第几个(:first-of-type;:last-of-type;:nth-of-type(n);:nth-last-of-type(n);:only-of-type;)
             nth-child(odd);nth-child(even);
    * 同级别奇偶数（不分类型）
             nth-of-type(odd); nth-of-type(even);
    * 同级别同类型的奇偶数
             :nth-child(nx+y);自定义的，n为计数器
  * 属性选择器 
    
    * 标签[attribute]
    * 标签[attribute=value]
    * 属性取值以什么开头  选择器[attribute^=value]
    * 属性取值以什么结尾  选择器[attribute$=value]
    * 属性取值包含什么    选择器[attribute*=value]
    
3.嵌套盒子内的水平垂直居中
     
  * 给外盒子设置padding(首推)：增加padding和border都会改变盒子的宽高；
                                如果想盒子的大小不变，则修改width或者 增加box-sizing:border-box.
     
     
  * 给内盒子设置margin：    
    
    * 如果给内盒子设置了顶部外边距(margin-top),外面盒子也会被顶下来，如果不想外盒子顶下来 就给外盒子添加边框(border)或者overflow:hidden;
    
  * 利用margin:0 auto;来使里面的盒子在外面盒子内部居中.垂直居中就通过改变0的值[(外盒高-内盒高)/2].
  
4.盒子居中和内容居中

  * 盒子水平居中 margin:0 auto;
  
  * 内容
    
    * 水平居中 text-align:center;
  
    * 垂直居中：一行文字时 line-height=height；多行文字时 利用padding属性

5.overflow:hidden;的作用

  * 清除浮动.IE6不兼容
```
添加如下代码：
      (给第一个盒子).box1{
                    *zoom:1;
                  }
                       
```
  * 嵌套盒子中，内盒子设置了margin-top,为了不让外盒子被顶下来可设置此属性.
  * 将超出标签范围的内容裁剪掉.

6.绝对定位中的水平居中(margin: 0 auto;不能用)
```
     left:50%;
     margin-left:-的元素的一半(要水平居中的元素)
```
