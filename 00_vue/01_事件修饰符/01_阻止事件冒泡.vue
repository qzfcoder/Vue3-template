
<template>
  <div class="parent" @click="onClickParent">
    我是爸爸
    <div class="child" @click="onClickChild">
      我是儿子
    </div>
  </div> 
</template>

<script>
export default {
  // 通过点击子组件 父组件的事件也会被触发，
  // 阻止方式一：
  // 添加.stop修饰符在子组件的点击事件上
  // 阻止方式二：
  // event.stopPropagation 在子组件的方法最后添加
  name: 'stop',
  methods: {
    onClickParent () {
      console.log('我是爸爸')
    },
    onClickChild () {
      console.log('我是儿子')
    }
  }
}
</script>
