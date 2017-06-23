#this

1.this指向取决于函数调用的对象

2.this出现的四种情况

  * 作为函数调用：函数直接被调用，this指向全局对象window
```
function make(x){
    this.x=x;
}
make(5);//直接调用，会把this指向全局对象，
相当于隐式声明了一个全局变量x(grobal.x=5)
```
    
     * 对于内部函数(声明在另一个函数体内的函数)来说，这种绑定到全局对象的方式会产生问题
     
  ```
var point={
    x:0,
    y:0,
    moveTo:function(x,y){
        var that=this;
      var moveX=function(x){
       this.x=x;
    },
      var moveY=function(y){
       this.y=y;
    }
      moveX(x);//直接调用，this指向全局变量
      movey(y);
    }
}
point.moveTo(1,2);
  ```

  ```
var point={
    x:0,
    y:0,
    moveTo:function(x,y){
      var that=this;//保留了this指向point
      var moveX=function(x){
       that.x=x;//that指向ponit
    },
      var moveY=function(y){
       that.y=y;
    }
      moveX(x);//直接调用，this依然指向全局变量
      movey(y);
    }
}
point.moveTo(1,2);
  ```

  * 作为对象方法调用：this被自然绑定给该对象
  
  ```
  var point={
  x:0,
  y:0,
  moveTo:function(x,y){
  this.x=this.x+x;
  this.y=this.y+y;
  }
  }
  point.moveTo(1,2);
  ```

  * 作为构造函数调用：this指向有构造函数创建的对象实例上
  * 使用apply call调用：可以切换函数执行的上下文环境(this指向)

#this语法糖

1.转换为call方法的方式，与call本身的方法不冲突

2.两种情况

  * foo()--->foo.call(window)
  * obj.foo()--->obj.foo.call(obj)

3.foo()--->foo.call(window)  
  
  * 把直接调用调解为一种语法糖，在严格模式下，不是window而是undefined
  * 匿名函数的自调用也是如此，指向window
    
    ```
    (function(x){ })('')--->(function(x){}).call(window)
    ```

4.obj.foo()--->obj.foo.call(obj)或者obj.child.foo()--->obj.child.foo.call(obj.child)

  * 函数作为对象方法被调用
  * 作为对象方法内部的函数，会发生问题
    
    * 解决方法是应该保留外部函数的this指向到内部函数里面
