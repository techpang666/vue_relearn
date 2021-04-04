<template>
  <div>
    <h1>
      这是Vue生命周期的面试题专栏
    </h1>
  </div>
</template>

<script>

/**
 * @description 什么是生命周期
 * 
 * Vue实例从创建到销毁的过程 就是生命周期
 * 
 * 也就是从开始创建/初始化数据/编译模板/挂载DOM-渲染/更新-渲染/卸载等一系列的过程 我们称这是Vue的生命周期
 * 
 */

/**
 * @description Vue生命周期的作用是什么
 * 
 * Vue所有的功能实现都是围绕其生命周期进行的 在生命周期的不同阶段调用对应的钩子函数 可以实现组件数据管理和DOM渲染两大重要功能
 * 
 * 生命周期中有多个事件钩子 在控制整个Vue实例的过程时 可以形成更好的逻辑关系
 * 
 */

/**
 * @description 第一次页面加载时会触发哪几个钩子
 * 
 * beforeCreate/created/beforeMount/mounted
 * 
 */

/**
 * @description vue的生命周期列表
 */

/*

常规8个
beforeCreate(创建前)
created(创建后)
beforeMount(挂载前)
mounted(挂载后)
beforeUpdate(更新前)
updated(更新后)
beforeDestroy(销毁前)
destroyed(销毁后)

其实11个
beforeCreate(创建前)
created(创建后)
beforeMount(挂载前)
mounted(挂载后)
beforeUpdate(更新前)
updated(更新后)
beforeDestroy(销毁前)
destroyed(销毁后)
activated(激活时)
deactivated(停用时)
errorCaptured(错误调用时)

常用2个
created(创建后)
mounted(挂载后)

*/

/**
 * @description 服务端渲染时不被调用的生命周期
 * 
 * mounted(挂载后)
 * destroyed(销毁后)
 * activated(激活时)
 * deactivated(停用时)
 * 
 * 只有初次渲染的时候才在服务端进行
 * beforeUpdate(更新前)
 * 
 */

export default {
  beforeCreate () {
    console.log('创建前');

    /*
    
    该函数执行在
    组件创建/数据观测(data observer)/(event/watcher)事件配置之前
    实例初始化之后被调用

    在该阶段组件未创建 不能访问数据
    组件中的data/ref均为undefined
    
    */
  },
  created () {
    console.log('创建后');
    
    /*
    
    在组件创建完成后立即调用
    
    在这一步 实例已经完成了数据观测/属性和方法的运算/(watch/event)事件回调

    但是还没有渲染成html模板 组件中的data已经存在 可以进行操作
    但是el仍然是undefined 因为挂载阶段还没有开始 $el属性尚不可用
    
    一般我们可以将对数据的初始化/页面的初始化的请求放到这里 例如结束loading事件
    
    */
  },
  beforeMount () {
    console.log('挂载前');

    /*
    
    该函数在挂载之前被调用
    
    该阶段页面上还没有渲染 data已经初始化完成 ref还不可以操作 render函数首次被调用
    
    可以访问数据 编译模板结束 虚拟dom已经存在
    
    */
  },
  mounted () {
    console.log('挂载后');
    
    /*
    
    该函数是在组件挂载完成之后执行的

    这时候el被$el替换 已经可以操作ref了
    一般在这个阶段请求数据
    filter过滤器也是在这个阶段生效

    服务器渲染期间不被调用
    
    */
  },
  beforeUpdate () {
    console.log('更新前');
    
    /*
    
    在数据更新时调用 在虚拟dom更新前
    
    在特殊情况下 可以讲将更新前的数据存起来 放到之后使用

    这里适合在更新前访问现有的dom 比如移除事件监听器

    该钩子只有初次渲染会在服务端进行
    
    */
  },
  updated () {
    console.log('更新后');

    /*
    
    由于数据更改导致的虚拟dom重新渲染和打补丁 在这之后会调用该钩子
    
    当这个钩子被调用时 组件dom已经更新 所以你现在可以执行依赖于dom的操作

    页面也完成了更新 此时的data数据是最新的 同时页面上呈现的数据也是最新的
    
    */
  },
  beforeDestroy () {
    console.log('销毁前');

    /*
    
    在实例销毁之前调用
    
    这里依然可以操作 可以在这里清除定时器 防止内存泄漏
    
    */
  },
  destroyed () {
    console.log('销毁后');
    
    /*
    
    在销毁后调用
    
    所有子实例被销毁 所有的事件监听器会被移除
    
    在服务器渲染期间不被调用
    
    */
  },
  activated () {
    console.log('激活时');

    /*
    
    被keep-alive缓存的组件激活时调用

    该钩子在服务器端渲染期间不被调用
    
    */
  },
  deactivated () {
    console.log('停用时');

    /*
    
    被keep-alive缓存的组件停用时调用

    该钩子在服务器端渲染期间不被调用
    
    */
  },
  errorCaptured (err, vm, info) {
    console.log('错误调用时');

    /*
    
    当捕获一个来自子孙组件的错误时被调用(vue2.5新增的)

    此钩子会收到三个参数
    错误对象/发生错误的组件实例/一个包含错误来源信息的字符串
    
    此钩子可以返回false以阻止该错误继续向上传播
    
    */
  }
}
</script>

<style>

</style>