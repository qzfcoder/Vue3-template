<template>
  <div class="self" @click.self="onClickSelf">
    <div class="inner" @click="onClickInner"></div>
  </div>
</template>

<script>
// 不加self的话，点击内部元素也会触发父组件的事件，加了self之后只有触发事件本身的元素
export default {
  name: 'self',
  methods: {
    onClickSelf () {
      console.log('我是self节点')
    },
    onClickInner () {
      console.log('我是inner节点')
    }
  }
}
</script>


