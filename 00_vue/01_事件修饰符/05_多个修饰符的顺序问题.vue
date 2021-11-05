<template>
  <div class="order">
    <div class="order-0">
      <a
        href="https://juejin.cn/"
        class="order-parent"
        @click.self.prevent="onClickParent"
      >
        我是父节点，会跳转掘金
        <br />
        <span class="order-child" @click="onClickChild"> 我是子节点 </span>
      </a>
      <hr />
    </div>
    <div class="order-2">
      <a
        href="https://juejin.cn/"
        class="order-parent"
        @click.prevent.self="onClickParent"
      >
        我是父节点，无法跳转掘金
        <br />
        <span class="order-child" @click="onClickChild"> 我是子节点 </span>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  // 首先可以明确的是点击上面和下面的子节点都不会触发父节点的点击事件

  // 点击下面的父节点会打印出我是父节点，但是不会跳转掘金

  // 点击上面的父节点会打印出我是父节点,也不会跳转掘金

  // a@click.self.prevent="onClickParent"的意思是当点击的元素是a元素本身时，会阻止默认事件（可以解释3，不会发生跳转），并且执行onClickParent回调。
  // 而点击span元素时，由于冒泡的缘故，点击事件会传递给a，但是此时a会判断出该事件不是由自身触发的也就不会阻止默认事件(此时也就发生跳转了)，当然也不会触发onClickParent回调
  // 同理来我们分析一下a@click.prevent.self="onClickParent"
  // 不管是子节点还是自身点击，都是先阻止默认事件，只有当触发点击事件是a元素本身时才会执行onClickParent回调函数。

  // 使用修饰符时候
  // @click.self.prevent="onClickParent" ： 只会阻止自身的点击
  // @click.prevent.self="onClickParent" ： 会阻止所有的点击
  name: "order",
  methods: {
    onClickParent() {
      console.log("我是父节点");
    },
    onClickChild() {
      console.log("我是子节点");
    },
  },
};
</script>
