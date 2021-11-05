<template>
  <div class="native-custom">
    <input type="text" @keydown="onKeydown">
  </div>
</template>
<script>
// 我们知道在自定义组件上，只能监听自定义事件，一些原生事件（比如click）是没有办法直接触发的，但是使用.native修饰符可以帮我们办到这点
export default {
  name: 'nativeCustom',
  methods: {
    onKeydown () {
      this.$emit('onKeydown')
    }
  }
}
</script>

<template>
  <div class="native">
    <!-- 加上.native之后原生事件才得以监听成功 -->
    <NativeCustom @onKeydown="onKeydown" @click.native="onClick" />
  </div>
</template>

<script>
import NativeCustom from '../../components/native.vue'
export default {
  name: 'native',
  components: {
    NativeCustom
  },
  methods: {
    onKeydown () {
      console.log('onKeydown')
    },
    onClick () {
      console.log('onClick')
    }
  }
}
</script>



