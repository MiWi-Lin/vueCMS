vue_cms-x
====
可视化拖拽系统

#20180814更新

1.加入组件code split优化

2.项目目录出入口多页面打包完成，拆分view和edit两个页面，功能单一性；
    
      view只负责渲染组件用户浏览页面组件的加载
      
      edit加载更多UI和JS插件等
      
      view和edit拆分有助于后期开发的可观和操作性
      
3.埋点的加入

##使用说明
```
npm install

npm run dev //本地运行 访问可视化编辑访问edit.html，显示效果访问view.html

npm run pre //预发打包

npm run build

```
componnet ====>编辑可视化组件

viewComponents  ====>  用户访问页面查看组件

layout  ====>   可视化编辑结构组件

server  ====>   所有相关请求接口文件配置

widgets ===>   组件列表编辑配置

plugins ===>   开发vue插件用，目前项目中用到的弹框等都是elementUI那一套，并没有自己开发，只写了个toast的例子在里边


组件开发步骤：

1。src/components里创建vue文件，同时在index.js里创建异步组件方法例`ordinaryProduct:()=>import('./ordinaryProduct')`

2。widgets-->widgets.js配置相关组件信息

由于项目中设计到公司的一些域名，可能直接跑无法运行；

clone后要修改个文件：server中api文件中的createObject接口，这个接口是在拖拽后从后端请求组件配置接口，接口格式已经放到easy mock中；或者直接改掉store中getDefaultConfig方法，自己把组件配置写在本地一个文件中，这样拖拽时就可以看到效果

整个可视化项目中心都在store和render文件里，viewRender只是clone了一下并删掉了一些view时没用的功能；

核心:vuedraggable 和 vue的component组件，一切都围绕这两块做的

分享整个可视化项目主要是给大家提供一个思路，（项目中用到了elementUI的一些上传，按钮，弹框的UI，所以打包后vendor比较大，也没有把view和edit单独打包公用插件）代码有瑕疵的地方还望指出，理想情况下如果创建一套这样可视化拖拽系统，其实应该加入node，虽然这一套可视化加入了异步加载组件，但如果用户访问我们搭建好的页面时还是需要加载js后才会出现页面，这各部分如果有node加入的话，用SSR效率和可用性更加完美，毕竟我们搭建的页面时给用户看的；

欢迎大神指导意见

整个项目从搭建开始都是作者一人在搞，项目近，任务重，请轻喷！！！

原创不易，多多支持；

**TODOS**

copy 编辑配置有问题

整体结构目录优化，重灾区top.vue，util文件夹，edit.js等文件调整和文件内部拆分颗粒





