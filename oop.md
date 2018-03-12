Object Orientical(oo编程)
命名空间
a = a || {}
js小技巧
五个falsy  '' null undefined 0 NaN
1&&0 //0
1&&0&&2 //0
0后边不执行
1&&0&&console.log(3)//0
console.log(3)  //值是undefined

或  且 的值基本上不可能是true/false
1 || 2 //1

var a = b || {}
if(b){
  a = b
}else{
  a = {}
}

var app ={} //危险代码
var app = app || {}
if(app){
  app =app //废话 没什么作用
}else{
  app = {}
}
名字全都放在一个空间里

类

```
this

1.

button.onclick = function(){
console.log(this)
}
//button

mdn  onclick   //触发事件的元素的引用
 
button.addEventListener{
console.log(this)
}
//button

 mdn addEventListener 触发事件的元素的引用

$('ul').on('click','li'/*selector*/,function(){
console.log(this)
//li元素
})
jquery源码


button.onclick = function f1(){
console.log(this)
}
button.onclick.call({name:'frank'})//{name:'frank'}

升级
function X(){
  return object = {
    name:'object',
    f1(x){
      x.f2()
    },
    f2(){
      console.log(this)  //A
    }
  }
}
var options = {
  name:'options',
  f1(){} ,
  f2(){
    console.log(this) // B
  }
}
var x = X()
x.f1(options)


答案：B  options
x.f1(options)调用object, 传入options，options.f2()



function X(){
  return object = {
    name:'object',
    f1(x){
      this.options = x
      this.f2()
    },
    f2(){
     this.options.f2.call(this)  //C    object/options
    }
  }
}
var options = {
  name:'options',
  f1(){} ,
  f2(){
    console.log(this) // D  object/options
  }
}
var x = X()
x.f1(options)
d object

function X(){
  return object = {
    name:'object',
    f1(x){
      this.options = x  
      // 3. object.f1(x) ，所以这里的  this === object，结果为：object.opitons === options1
      this.f2()
      // 4. this === object,意为：object.f2()
    },
    f2(){
     this.options.f2.call(this) 
      // 5. options1.f2.call(this)  === object.f2()
      // options1.f2.call(this) 的  this 为 object  
    }
  }
}
var options1 = {
  name:'options',
  f1(){} ,
  f2(){
    console.log(this) 
    // 6.  options1.f2.call(this) 的  this 为 object  
    // console.log(this)  === console.log(object) 
  }
}
var x = X()		//1. x === object
x.f1(options1)   //2.  x.f1(options) === object.f1(options)

```
js的new在做什么
var object = new Object()
加上自有属性 空
object.__proto__ === Object.prototype

var array = new Array('a','b','c')
array.__proto__ === Array.prototype
Array.prototype === Object.prototype
Array.__proto__ === Function.Prototype //浏览器写

