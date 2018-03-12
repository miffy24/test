
## sign_up.html
1. 先做一个sign_up的路由
2. 做sign_up.html页面内容
3. 引入jqery
4. 监听提交，阻止默认事件，得到need作为hash的key，遍历need获得表单name，把得到的name作为hash的value
5. 再给post写个路由
6. 读取用户输入的数据，用户post了sign_up，服务端读取第四部分，读取body，从body里边得到字符串
    - node http get post data 极限用户输入一万个字符
    - 写一个函数封装将用户输入的数据push结束的时候contact

    客户端从表单里获得信息变成字符串，服务端把字符串还远成分开的字符串（还原成想要的结构）
    做错误提示，提示不友好
    找到所有error为空
    如果格式都是对的把 数据存下来
7. 创建一个文件放数据
   - 有个bug @用40%代替
   - 如果邮箱已经注册了用if判断
8. 用户登录
    - sign_in页面和响应

8. 密码加密


cookie 按域名分组，只能看见自己 httponly 防止js改
9. 首页做读数据 nodejs read cookie
request.headers.cookie
多个cookie  用；分隔，用hash，遍历cookie存入数据，
获取hash的email再去users里边找，
把users变成数组，遍历users，如果俩个Email相同，登录了
10. 登录后展示用户
用户打开sign_up 注册发送post数据 server写数据，告诉用户注册成功了
用户打开登录页面提交是发post给Email和password，如果在就登录，反之注册
 给setcookie ,浏览器记录下来，用户在打开首页，浏览器带上cookie，读cookie
 通过email查找users里的信息返回html时填入对应信息，响应回去
 另一个用户打开首页给所有人看的一样的信息
 










 登录成功，cookie 内容是sign_in_email:1@chen.com
 访问首页，请求cookie
 服务器，读cookie
 cookie可以被用户篡改


服务器通过cookie给用户一个sessionID（随机数）,
sessionID对应服务起里的一小块内存
每次用户访问服务器时候，
服务器就通过sessionID读取对应session，
就可以获得用户隐私信息

 在cookie添加sessionID，放入session 


cookie
1. 服务器通过Set-Cookie头给客户端一串字符串
2. 客户端每次访问相同域名的网页时，必须带上这段字符串
3. 客户端在一定时间内保存这个cookie
4. cookie 默认在用户关闭页面后就失效，后台代码可以任意设置cookie的过期时间
5. 大小在4kb左右

Q：如果吧用户iD存入cookie用户可以直接改
session
1. 将sessionID（随机数）通过cookie发给客户端
2. 客户端访问服务器，服务器读取所有sessionID
3. 服务器有一块内存（对象）保存所有session
4. 通过sessionID我们可以用得到对用户的隐私信息如id，emial
5. 这块内存（哈希表）就是服务器上所以session

session是服务器上的hash表
localstorage是浏览器上的hash表

localstorage  不占内存
方法：
setItem
getItem
JSON.Stringify


localStorage使用
持久化存储
页面刷新也可以把数据保存到本地文件，用来在以后使用

记录有木有提示用户

特点：
1. localStorage 跟http无关
2. HTTP不会带上loaclstorage的值
3. 只有相同域名的页面才能互相读取LocalStorage（没有同源那么严格）
4. 每个域名localStorage最大存储量为5Mb（每个浏览器不一样）
5. 常用场景：记录有木有提示过用户（没有用的信息，不能记录密码）
6.LoaclStorage永久有效，除非用户清理缓存
control shift d 清楚所以cookie和locs


sessionStorage  (会话存储）
1,2,3,4同上
5. sessionStorage在用户关闭页面就会失效



Q：cookie和session关系
session基于cookie实现
Q：cookie和localStorage区别
cookie会被浏览器带到服务器，localStorage不会被带到服务器
cookie 4k  localStorage 5Mb

Q：
localStorage 和sessionStorage
sessionStorage在用户关闭页面（会话结束）后失效


不基于cookie的session

cookie和localStoragecookie让访问变慢
前端不要写cookie，用localStroage
腾讯前端随便在页面写cookie，访问首页慢，cookie太多了

缓存控制 Cache-Control

HTTP缓存
Web性能优化一部分

如何css和js访问变快
cache control mdn

setHeader('cache-control','max-age=0')


首页不能设置cache-control
用户没有办法获取最新版本

首页不要设置缓存

更新缓存
1. 改url 加查询参数

expires
以前  expires
现在 cache-control

expires不靠谱，设置时间点，ca设置时间长度，优先使用cache


Last-Modified 

md5
摘要算法
如果修改越少，差异越大


ETag
nodejs md5

```
let fileMd5=md5(string)
response.setHeader('ETag',fileMd5)缓存与 304 的区别
```
缓存没有请求。
ETag 304 有请求，有响应，但是响应没有第四部分。
