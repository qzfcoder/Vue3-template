<template>
  <div class="lazy">
    <div class="lazy-item">
      <input type="text" v-model="text">
      <p>无.lazy: {{ text }}</p>
    </div>

    <div class="lazy-item">
      <input type="text" v-model.lazy="text2">
      <p>.lazy: {{ text2 }}</p>
    </div>
  </div>
</template>

<script>
// v-model大家都很熟悉，默认情况下，每次input事件触发的时候都会将输入框的值与其绑定的数据进行实时同步。但是如果想要实现光标离开的时候再更新数据如何实现呢？
export default {
  name: 'lazy',
  data () {
    return {
      text: '',
      text2: ''
    }
  }
}
</script>


