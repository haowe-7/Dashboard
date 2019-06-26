# 架构设计、详细设计（BCE方法）到应用程序框架映射指南 

## 架构设计

`施工中`

## 代码结构

`施工中`

## BCE关系

- Boundary层：通过Web页面提供用户界面
  - LoginPage：一开始进入的页面，提供登录/注册功能。
  - MainPage：提供任务列表供用户浏览，可对任务进行评论。
  - InfoPage：显示与用户相关的信息，如发布的任务、参与的任务。
  - DetailPage：显示任务详情，可申请参与任务。
  - SettingPage：可修改用户个人信息。
- Controller层：处理UI和Entity 类的一些触发事件 
  - 在`Controller`层中处理来自 `Boundary` 层的事件，执行业务逻辑，对`Entity`层中的数据进行C、R、U、D操作。
- Entity层：储存用户数据、任务数据等
  - User：用户数据
  - Task：任务数据
  - Comment：评论数据
  - Message：消息数据







