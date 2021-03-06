# project-SPH
## 1 项目基础： 使用vue-cli脚手架初始化项目。
- APP目录讲解：
  - node_modules文件夹 : 项目依赖文件夹；
  - public文件夹 ：一般放置一些静态资源文件。注意：放在该文件夹中的静态资源，webpack进行打包的时候，会原封不动打包打包道dist文件夹中。
  - src文件夹：
    - assets文件夹 ： 一般放置静态资源，放置多个组件共用的静态资源。注意：放置在assets文件夹里面的静态资源在webpack打包的时候，webpack会把静态资源当成一个模块，打包到JS文件里面。
    - components文件夹： 一般放置的是非路由组件（全局组件）。
    - App.vue : 唯一的根组件。
    - main.js ：程序的入口文件，也是整个程序中最先执行的文件。

- babel.config.js：配置文件
- package.json：项目信息记录，记录项目叫什么、有什么文件、有哪些依赖
- package-lock.json： 缓存性文件

## 2 项目配置
#### 2.1 浏览器自动打开(package.json)
```
    "serve": "vue-cli-service serve --open",
```
#### 2.2 eslint校验功能关闭
```
  lintOnSave:false
```

#### 2.3 src文件夹配置别名
```
    "paths": {
      "@/*": [
        "src/*"
      ]
    },
```


## 3 项目路由分析 vue-router
- 前端所谓的路由可以看成是：kv键值对。key：是URL，地址栏中的路径；value：相应的路由组件。
- 页面结构
  - 主要分为：上、中、下三部分
  - 路由组件
    - Home ：首页路由；
    - Search ： 搜索部分路由；
    - login  ： 登录路由；
    - register：注册部分的路由；
  - 非路由组件：
    - Header：头部路由（使用在首页和搜索页）
    - Footer：页脚路由（使用在首页和搜索页）

## 4 完成路由组件Header和footer

#### 项目开发流程：
1. 书写静态页面（HTML和CSS）
2. 拆分组件
3. 获取服务器的动态数据并展示
4. 完成相应的动态业务逻辑

注意：
- 创建组件的时候：组件结构 + 组件的样式 + 图片资源
- 本项目采用less样式，浏览器不识别less样式，需要通过less、less-loader进行处理less，把less样式变为css样式，浏览器才能够识别。


#### 4.1 使用组件的步骤
- 创建：创建或定义组件
- 引入：在App.vue中引入组件
- 注册：在App.vue中的components中注册组件
- 使用：在template中进行使用
