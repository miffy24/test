留言系统数据库

MVC：按功能划分模块

view：js 代码所操纵的视图（HTML），负责显示给用户和通知 controller（控制器）

Model：view（视图）所需要的所有的数据操作,包括：

初始化数据
读取数据
存入数据
负责和向 server（服务器）请求数据和响应 server（服务器）

controller：所有的逻辑操作，负责监控和更新 view（视图） + 调用和接收 model（数据）

思路：

获取 view
设置 model
初始化 AV 对象
读取数据
存储数据
设置 controller
初始化函数 init
调用 model 的初始化 AV 对象
读取数据。调用 model 的读取数据函数
获取总数
遍历，创建 li 元素并添加相应的数据，将li 添加到 HTML 中
绑定事件
form 提交表单事件：
阻止事件的默认行为
提交按钮移除激活状态
调用 model 的存储数据函数
存储数据成功后
改变留言总数
创建 li 元素并添加输入内容，将 li 添加到 HTML 中
将输入框重置
输入框的 input 事件：验证输入框是否有值，有值才能留言
