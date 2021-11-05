<template>
  <div class="sync-parent">
    我是父组件: {{ text }}
    <Child :text.sync="text" />
  </div>
</template>
<script>
// 当我们想要在父组件和子组件之间对某个属性值进行双向绑定时,有什么便捷的方式？是的只要.sync修饰符即可办到

import Child from './child.vue'

export default {
  name: 'SyncParent',
  data () {
    return {
      text: 'parent'
    }
  },
  components: {
    Child,
  }
}
</script>

<template>
  <div class="child">
    我是子组件: 
    <input type="text" v-model="value" @input="onInput">
  </div>
</template>

<script>
export default {
  name: 'child',
  props: {
    text: {
      type: String
    }
  },
  data () {
    return {
      value: this.text
    }
  },
  methods: {
    onInput () {
      // 注意这里，必须是update:xxx的形式xxx即属性prop
      this.$emit('update:text', this.value)
    }
  }
}
</script>



