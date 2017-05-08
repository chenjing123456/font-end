#原型

##Object.create的方法

1.es5中新引入的方法，功能是实现继承，创建一个 原型继承 自参数的对象。就是返回新对象，原型是参数中表示的对象。

```
    var o={
        sayHello:function(){
            console.log('hello');
        }
    }
    var o1=Object.create(o);//创建一个新对象O1,该对象的原型是o
```
```
eg:创建一个对象，有数组的方法，添加值并且遍历出来
var a=Object.create([]);
a.push('2','2','3','3');
for(var i=0;i<.length;i++){
    console.log('['+i+']'+'='+arr[i]);
}
```

2.如果浏览器不支持Object.create属性（兼容浏览器）
```
//方法一：不能改变系统内置的对象,所以不能用
    if(!Object.create){
  Object.create=function(){};
  }
```
```
方法二：兼容浏览器，函数要实现原型继承，返回的对象应该继承obj
function inherit(obj){
      if(Object.create){
        return Object.create(obj);
      }else{
        function F(){};
        F.prototype=obj;//利用直接替换把原型指向obj
        return new F();
    }   
    }
    var arr=inherit([]);
```

##对象的原型链

###原型链

   * 凡是对象就有原型

   * 原型也是对象

   * 因此凡是给定一个对象，那么就可以找到它的原型，原型又是对象，原型又有原型，如此往复，就构成一个对象序列，就称该结构为原型链

###原型链结构

1.默认的原型链结构
  
   * 凡是使用构造函数创建出来的对象，并且没有利用赋值的方式修改原型，就说该对象保留默认原型。
   * 默认原型链的结构是什么样的？
```
function Person(){}
var p=new Person();
```
   * 原型链结构就是：当前对象-->构造函数.prototype-->Object.prototype-->null

2.修改的原型链结构
   
   * 在实现继承的时候有时会利用替换的方法实现原型继承，那么原型链结构会发生改变
   * 
```
    function F(){};
    F.prototype=[];
    var a=new F();
```
   * 修改的原型链结构：a-->[]-->Array.prototype-->Object.prototype-->null

##原型式继承


