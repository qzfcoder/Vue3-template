<template>
  <div class="custom">
    <input type="text" @keydown.q="f1Keydown" />
  </div>
</template>

<script>
export default {
  // Vue.config.keyCodes = {
  //   q: 81
  // }
  name: "custom",
  methods: {
    f1Keydown() {
      console.log("按下了q");
    },
  },
};
</script>
