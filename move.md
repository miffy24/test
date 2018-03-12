写1234567890动,让字动   
var result = '1234567890'
var n = 0
var id = setInterval(()=>){
  n += 1
  document.body.innerHTML = result.substring(0,n)
  console.log("one")
  if(n >= result.length){
    window.clearInterval(id)
  }
},500)
问题body{
  background:red;
}么有保留回车空格  

回车tab空格无论几个看成一个空格
pre标签 预览效果
问题没有出现效果  
<style id ="styleTag"></style>
<pre id ="code"></pre>
styleTag.innerHTML =result.substring(0,n)

code.innerHTML =result.substring(0,n)
代码高亮 prism库

一开始选择器黑色

异步：不等结果，直接下一步
那我怎么拿到结果
回调可以

回调是拿到异步结果的一种方式
回调也可以拿同步结果

让黄牛买票，然后站着等（同步）
让黄牛买票（告诉黄牛，买到票call我），然后做别的

告诉黄牛，买到票就打回电话给我
when
