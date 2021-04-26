<template>
  <div>
    <h1>
      这是组件之间的通信专栏
    </h1>
    <test :money="count" :obj="myobj">
      通过props将数据在组件树中继续自上而下的传递
    </test>
    <test add-action="fatherFn">
      通过$emit和@作为信息的向上传递
    </test>
  </div>
</template>

<script>

/**
@description 组件之间的通信方式

- 父传子(props)
- 子传父($emit)
- 非父子
- vuex
 */

export default {
  // 父传子(props)测试代码
  props: {
    money: {
      type: Number,
      default: 1
    },
    obj: {
      type: Object,
      default: () => {
        return {
          name: '张三',
          age: 18
        }
      }
    }
  },
  mounted () {
    // 子传父($emit)测试代码
    this.$emit('add-action')
  }
}
</script>

<style>

</style>