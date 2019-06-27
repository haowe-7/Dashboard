

# 架构设计、详细设计（BCE方法）到应用程序框架映射指南 

## 架构设计

`施工中`

## 代码结构

### 前端

```
|-- build
|	|-- build.js
|	|-- check-versions.js
|	|-- logo.png
|	|-- utils.js
|	|-- vue-loader.js
|	|-- webpack.base.conf.js
|	|-- webpack.dev.conf.js
|	|-- webpack.prod.conf.js
|-- config
|	|-- dev.env.js
|	|-- index.js
|	|-- prod.env.js
|	|-- test.env.js
|-- src
|	|-- api
|	|	|-- collects.js
|	|	|-- comments.js
|	|	|-- participate.js
|	|	|-- tasks.js
|	|	|-- users.js
|	|-- assets
|	|	|-- back.png
|	|	|-- backgrond.png
|	|	|-- icons8-bookmark-32.png
|	|	|-- icons8-edit-32.png
|	|	|-- icons8-share-3-32.png
|	|	|-- icons8-speech-bubble-32.png
|	|	|-- logo.png
|	|	|-- search.png
|	|	|--	盈小钱.png
|	|	|-- 盈小钱logo.png
|	|	|-- 盈小钱logo2.png	
|	|-- components
|	|	|-- QuesManage
|	|	|	|-- Data.vue
|	|	|	|-- Datepicker.vue
|	|	|	|-- Edit.vue
|	|	|	|-- Fill.vue
|	|	|	|-- Header.vue
|	|	|	|-- List.vue
|	|	|-- Setting
|	|	|	|-- PersonalInfoComponent.vue
|	|	|	|-- PersonalPrivacyComponent.vue
|	|	|-- CategoryPage.vue
|	|	|-- DeliverTaskDetailPage.vue
|	|	|-- Identify.vue
|	|	|-- Login.vue
|	|	|-- MainPage.vue
|	|	|-- MyInfoList.vue
|	|	|-- MyPublishTask.vue
|	|	|-- PasswordBackDialog.vue
|	|	|-- PublishDeliverTaskDetail.vue
|	|	|-- RecommandPage.vue
|	|	|-- Register.vue
|	|	|-- SettingPage.vue
|	|	|-- TaskApplicantPage.vue
|	|	|-- TaskBlock.vue
|	|	|-- TaskBriefInfoPage.vue
|	|	|-- TaskDiscussPage.vue
|	|	|-- TaskPage.vue
|	|	|-- TaskParticipatesPage.vue
|	|-- router
|	|	|-- index.js
|	|-- store
|	|	|-- modules
|	|	|	|-- tasks.js
|	|	|	|-- users.js
|	|	|-- getters.js
|	|	|-- index.js
|	|-- style
|	|	|-- _Data.scss
|	|	|-- _Datepicker.scss
|	|	|-- _Edit.scss
|	|	|-- _Fill.scss
|	|	|-- _List.scss
|	|	|-- public.scss
|	|	|-- reset.css
|	|-- utils
|	|	|-- data.js
|	|	|-- requests.js
|	|	|-- store.js
|	|	|-- urls.js
|	|-- App.vue
|	|-- main.js
|-- static
|-- test
|	|-- e2e
|	|-- unit
|-- README.md
|-- index.html
|-- package-lock.json
|-- package.json
```

### 后端

```
|-- backend
|	|-- auth
|	|	|-- helpers.py
|	|	|-- views.py
|	|-- celery
|	|	|-- config.py
|	|-- collect
|	|	|-- views.py
|	|-- comment
|	|	|-- views.py
|	|-- docker
|	|	|-- dev
|	|	|	|-- profile
|	|	|	|-- web_run
|	|	|-- python
|	|	|	|-- assets
|	|	|	|	|-- cmd.sh
|	|	|	|	|-- install.sh
|	|	|	|-- Dockerfile
|	|	|-- dockers-compose.yml
|	|-- docs
|	|	|-- docker.md
|	|-- message
|	|	|-- views.py
|	|-- migrations
|	|	|-- versions
|	|	|-- README.md
|	|	|-- alembic.ini
|	|	|-- env.py
|	|	|-- script.py.mako
|	|-- participate
|	|	|-- views.py
|	|-- submission
|	|	|-- views.py
|	|-- task
|	|	|-- helpers.py
|	|	|-- views.py
|	|-- tests
|	|	|-- test_init.py
|	|-- user
|	|	|-- views.py
|	|-- _init_.py
|	|-- app.py
|	|-- blueprint.py
|	|-- bootstrap.py
|	|-- models.py
|	|-- utils.py
|-- README.md
```

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







