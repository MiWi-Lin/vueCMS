想用vue做一个拖拽组件生成页面，目前遇到了一个瓶颈；

1：拖拽后删除操作没有思路；

2：现在右侧的配置项和中间显示区域双向绑定，需要每一个组件都要重复的写watch监听，我想在vuex的json tree变动的时候组件内自动变，不想每一个组件都要写一套相同的监听

3：发布功能不知怎么办，这个系统中想有个发布，点击发布后我通过接口给后端一个整体的json tree，当用户访问发布后的页面，我需要通过这个json tree来渲染页面只有可视区的代码，没有拖拽操作的代码，这块还不知如何做

求思路和建议https://github.com/ithack/vueCMS/issues

把代码放出来希望大家给点思路和建议！！！！
