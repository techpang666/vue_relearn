<template>
  <div>
    <h1>
      这是Vuex的面试题专栏
    </h1>
  </div>
</template>

<script>

/**
 * @description 什么是Vuex
 * 
 * Vuex是专门为Vue.js设计的状态管理模式 它采用集中式存储管理应用的所有组件的状态
 * 更改状态的唯一方法就是提交mutation
 * 
 */

/**
 * @description Vuex的核心模块
 * 
 * state/mutations/actions/getters/modules
 * 
 * state 存放的是数据源
 * mutations 用于处理同步操作
 * actions 用于处理异步操作
 * getters 相当于store的计算属性
 * modules 模块化store
 * 
 */

/**
 * @description Vuex解决了什么问题
 * 
 * 管理多个组件共享状态
 * 全局状态管理
 * 状态变更跟踪
 * 让状态管理形成一种规范 使代码结构更清晰
 * 
 */

/**
 * @description 怎么引用Vuex
 * 
 * npm安装vuex
 * 导入安装配置暴露注入vuex
 * 具体看store下的index.js
 * 
 */

/**
 * @description vuex的优缺点
 * 
 * vuex的优点
 * 解决了非父子组件的消息传递(将数据存放在state中)
 * 减少了ajax的请求次数 有些情景可以直接从内存中的state获取
 * JS原生的数据对象写法 比起localStorage 不需要做转换使用方便
 * 属于vue生态的一环 能够触发响应式的渲染页面更新(localStorage就不会)
 * 限定了一种可预测的方式改变数据 避免在大项目中数据的污染
 * 
 * vuex的缺点
 * 刷新浏览器的时候 vuex中的state会重新变为初始状态
 * 可以通过插件vuex-persistedstate解决
 * 
 */

/**
 * @description action和mutation有什么区别
 * 
 * 变更状态方式不同
 * action提交的是mutation 而不是直接变更状态
 * mutation是可以直接变更状态的
 * 
 * 操作方式不同
 * action可以包含任意异步操作
 * mutation只能是同步操作
 * 
 * 提交方式不同
 * action是通过this.$store.dispatch('ACTION_NAME', data)来提交
 * mutation是通过this.$store.commit('SET_NUMBER', 10)来提交
 * 
 * 接收参数不同
 * action第一个参数是context
 * mutation第一个参数是state
 * 
 * action和mutation的相同点
 * 第二参数都可以接收外部提交时传来的参数
 * this.$store.dispatch('ACTION_NAME', data)
 * this.$store.commit('SET_NUMBER', 10)
 * 
 */

/**
 * @description 为什么要使用vuex
 * 
 * 当项目遇到以下两种场景的时候
 * 
 * 多个组件依赖于同一状态的时候
 * 来自不同组件的行为需要变更同一状态的时候
 * 
 */

/**
 * @description vuex的应用场景
 * 
 * 大型项目才需要使用vuex
 * 小项目用组件传值/事件总线即可
 * 
 */

export default {

}
</script>

<style>

</style>