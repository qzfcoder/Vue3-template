<template>
  <div class="prevent">
    <a href="https://juejin.cn/" @click="onNoPrevent">点击跳转掘金</a>
    <br />
    <br />
    <a href="https://juejin.cn/" @click.prevent="onPrevent">阻止默认事件，无法跳转掘金</a>
  </div>
</template>

<script>
//.prevent轻松实现阻止默认事件,添加了prevent之后无法跳转掘金
// 方式二，在要阻止默认事件的方法中添加event.preventDefault()
export default {
  name: 'prevent',
  methods: {
    onNoPrevent () {
      console.log('未阻止默认事件')
    },
    onPrevent () {
      console.log('阻止默认事件')
    }
  }
}
</script>


