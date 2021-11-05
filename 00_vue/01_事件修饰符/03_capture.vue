<template>
  <div class="capture parent" @click.capture="onClickParent">
    父节点
    <div class="child" @click.capture="onClickChild">子节点</div>
  </div>
</template>

<script>
// 默认情况下，事件流是以冒泡(由里向外)的形式传递的,
// 加了capture之后，捕获（由外向里）
export default {
  name: 'capture',
  methods: {
    onClickParent () {
      console.log('我是父节点')
    },
    onClickChild () {
      console.log('我是子节点')
    }
  }
}
</script>


