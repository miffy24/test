form post和get请求 点view source 但是会刷新页面或新开页面
```
//get请求
<form action="xxx"method=get>
<input type="password"name="password">
<input type = "submit">
</form>
//post请求
```
a标签发送请求，当前页面或新开页面刷新
```

<a id = x href="/xxx">click</a>
<script>
x.click()
</script>
```
img 可以发请求，只能以图片形式

```
<script>
var image = document.createElement('img')
image.src='/xxx'
document.body.appendChild('child')
image.onload = function(){
console.log('s')
}
image.onerror = function(){
console.log('f')
}
</script>

```
生成link,只能以css,favicon形式展示
```
var link = document.createElement('link')
link.rel ='stylesheet'
link.href = '/xxx'
document.head.appendChild(img)
```
script可以发get，只能以脚本形式运行
```
var script =document.createElement('script')
script.src ='/yyy'
document.head.appendChild(script)

```
json出现
道格拉斯，数据交换语言   JavaScript精粹


undefined        没有
null             null
['a','b']        ["a","b"]
function fn()    么有
a.self=a         搞不定（么有变量）
{name:'frank'}   {"name":"frank"}
'frank'          "frank"
{__proto__}      么有原型链

 
json 没有抄袭function和undefined
json的字符串首尾必须是“”
区别
js和json是俩门语言，json抄袭js
么有undefined，函数，么有原型链，搞不定变量
浏览器必须保证
只有域名，协议，端口一模一样才允许发ajax请求
1.http://baidu.com 可以向http://www.baidu.com发AJAX请求么 no
cors

GET /xxx HTTP/1.1
HOST:jack.com:8002
Content-Type:application/x-www-url-encoded



response.statusText

1. js可以设置任意请求header
第一部分 request.open('get','/xxx')
第二部分 request.setHeader('content-type','x-www-form-urlencoded')
第四部分 request.send('a=1&b=2')
2.js可以获取任意响应么
第一部分 request.status/request.statusText
第二部分 request.getResponseHeader()/requst.getAllResponseHeaders()
第四部分 request.responseText


ajax 设置响应头，nodejs


promise规范
确定函数形式规范
then 多次处理结果，不需要取任何名字
jquery发现返回值的content-type 是json就转化为对象

小技巧：不要obj变量，直接传对象

自己封装ajax
window.jQuery.ajax = function({url,method,body,successfn,failfn,headers}){
  let request = new XMLHttpRequest()
  



}
successFn传回调，
callback === function 满足某种条件的函数

请求失败了是否有可能依然存在第四部分？ 有
第四部分只与content-type有关


success 的时候调用f1，f2
successFn:(x)=>{
f1.call(undefined,x)
f2.call(undefined,x)
}
设置head


jQuery.ajax{
success:()=>{}
error()=>{}
}


回调
frank.ajax({
  成功:function(){}
  失败:function(){}
})

jack.ajax(null,null,null,successFn,failFn)

fs.readFile(function(error,content){
  if (error){
  //失败
}else{
//成功
}
})

每个人封装风格不一样，要看文档，定义一个规范，promise
jqery看见json处理


return new Promise(function(resolve,reject)){}

ajax 必须返回promise，promise用then


