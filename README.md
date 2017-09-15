# vuetranse

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
## Vue第一次学习之旅 ##

 1. 项目内容
    项目学习自腾讯课堂米斯特吴老师的Vue实战项目 [在线翻译][1]
    学习 Vue-cli脚手架搭建
    Vue-CLI脚手架搭建
    Vue-组件嵌套
    Vue-资源请求
    Vue-连接第三方API
    Vue-组件数据传递
    Vue-第三方Bootstrap应用
    来完成在线翻译的一个小项目
 2. 项目分析
在线翻译由三个组件组成，APP主组件，翻译组件，翻译输出组件。
需要将翻译组件与翻译输出组件嵌套在主组件上，由翻译组件获取用户输入，然后向主组件传递用户输入事件（包括输入内容，按钮点击事件）,主组件获取事件后处理事件（获取文本，连接API 获取结果），主组件将结果输出到翻译输出组件，由翻译输出组件显示出来。
 3. 项目流程
   1.在命令行 通过 vue init webpack <projectName>建立vue-cli脚手架工程目录
   2.使用ide打开项目，通过npm run dev 运行项目
   3.删除默认项目，开始开发。
 4. 项目涉及知识点
    [Vue组件][2]是开发中的及基本单元。
    在vue脚手架中 一般使用[单文件组件][3]。
    在App.vue文件中 ，通过import导入组件 。


> `import Transtrion from './components/Transtrion'
import TransOutPut from './components/TranslateOutPut'
export default {
 name: 'app',
 components: {
    Transtrion,
    TransOutPut
  },
  }`


  之后就可以通过标签引用这两个模板
  子组件通过this.&emit()像父组件传递数据，另一个子组件通过props获取父组件中的数据。







  [1]: https://ke.qq.com/course/227593#term_id=100268603
  [2]: https://cn.vuejs.org/v2/guide/components.html#%E4%BD%BF%E7%94%A8%E7%BB%84%E4%BB%B6
  [3]: https://cn.vuejs.org/v2/guide/single-file-components.html
